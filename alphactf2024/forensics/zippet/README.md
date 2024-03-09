![image](https://github.com/NassimMansouri/writeups/assets/123596322/34d747b6-591b-4720-a2eb-c5c297e8b5fb)

We are presented with a zip file trying to unzip we'll be met by : 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/725757e7-18d7-4c3f-a37f-423931a6c544)

Tried fixing the zip file but being met with nothing

After reading for a long time about how zip files work and what each byte chunk does I extracted the compressed bytes 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/00802e2f-6dbc-4989-9427-40e55f46aae8)

the bytes in black are the compressed bytes

![image](https://github.com/NassimMansouri/writeups/assets/123596322/d26da6eb-8162-4437-8fd0-d7604fb30458)

Checking other bytes of the zip file we find that they used deflate method to compress the bytes

![image](https://github.com/NassimMansouri/writeups/assets/123596322/76ea5f24-dcc8-4d5e-aa7e-be4a016a37eb)

WE've got the following warning once we tried to extract the zip file 

```
warning [Chall.zip]:  35 extra bytes at beginning or within zipfile
```

Now all we need to do is to inflate the last 35 bytes of the compressed data 

Using a python script to do that 

```
import zlib

compressed_data = bytearray([0xF3, 0x31, 0x2E, 0x89, 0xCF, 0x75, 0x8D, 0x4F, 0x2F, 0x4D, 0x35, 0x35, 0x8D, 0x2F, 0xCF, 0x30, 0x29, 0x89, 0x37, 0xCF, 0x48, 0x8D, 0x0F, 0x48, 0x54, 0x51, 0x29, 0x37, 0x28, 0x4A, 0x89, 0x37, 0x2C, 0x06, 0x00])
print(len(compressed_data))
deflated_data = zlib.decompress(compressed_data, -zlib.MAX_WBITS)
decoded = deflated_data.decode('utf-8')
print(decoded)
    
```

![image](https://github.com/NassimMansouri/writeups/assets/123596322/f000e20a-3284-41f2-bd10-f4129b3918b8)

