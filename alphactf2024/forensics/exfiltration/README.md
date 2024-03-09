![image](https://github.com/NassimMansouri/writeups/assets/123596322/b8400c40-9f6d-4d0d-b868-7a4e0aed88ae)

After analyzing the pcapng file for a while I found suspcious ARP packets where the 3 bytes of the sender MAC adress are changing in each request

![Screenshot at 2024-03-09 10-10-29](https://github.com/NassimMansouri/writeups/assets/123596322/1ec5496a-f504-4cb1-bff5-073763bd87df)

Extracting the data 

```
tshark -r chall.pcapng -Y arp -T fields -e arp.src.hw_mac > data
awk '{print substr($0, length-7, 8)}' data > test
```

Decoding the data using cyberchef : 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/91baebdc-4ba4-457e-9781-478cd7d8d340)

AlphaCTF{MaC_eXF1LTR4tioN_tHrOUGH_4rP_P4Ck3Ts_ch4ll3NgE_4cc3pt3D}
