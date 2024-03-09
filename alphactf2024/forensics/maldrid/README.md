We've got a suspcious doc file checking with virus total 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/e2fff083-0b18-4c08-9dc5-aa09a4497a1c)

Now using olevba to deobsfucate vba macros 

```
$ olevba madridista_offer.doc --deobf
```

![image](https://github.com/NassimMansouri/writeups/assets/123596322/22d4309a-6ea1-4e36-b49c-9f3059fe42ad)

Following the deobsfucated pastebin url :

```
pastebin.com/raw/VL9iXQug
```

After decoding the first 2 base64 strings we get : 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/9ca1e9af-c797-44df-9bda-92d37bca6902)

```
AlphaCTF{192.168.194.28:6969}
```
