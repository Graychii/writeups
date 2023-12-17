For plan b-ackup :

We got an ansible vault 

I've first downloaded the back up file 

```
git clone https://github.com/4NG3L-4/Backeup.git
```

![image](https://github.com/NassimMansouri/writeups/assets/123596322/9436897f-88df-4fa7-a16f-a2bc2b6249eb)

Looks like we need a password to crack it

![image](https://github.com/NassimMansouri/writeups/assets/123596322/09be62ca-27ef-44f5-949a-7ca61cf45c71)

After checking commits logs 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/eb85f461-70c8-4cca-a858-460a01261bd1)

Seems like every commit the contents of my_secret.txt change
![image](https://github.com/NassimMansouri/writeups/assets/123596322/a226a0d2-da99-414b-9d05-3684fb944d72)

After trying each one of them and being met with failure I tried to make a combination between them by taking a letter of each file until I got 
"q7St!e@5BAy6jBAy"

After cracking the vault with the password and moving around we find .trash folder 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/5f5f33c3-ab76-4fc9-bc99-758b0f853251)

After using a tool like DS-Store-parser we get

![image](https://github.com/NassimMansouri/writeups/assets/123596322/9139a6ee-beef-4cd2-ba46-97137b607769)

We can see a lot of base64 strings and most importantly this :

![image](https://github.com/NassimMansouri/writeups/assets/123596322/064a67fd-c597-4d0d-8aa0-9278eeec9e9e)

Then I've made a file with all the b64 strings and went through them until I got

![image](https://github.com/NassimMansouri/writeups/assets/123596322/4d669286-030f-419c-abfb-e8c7f927ade7)

Bingo we got the first part

Moving on the second part, we see a folder called Keychains and after a little read on the internet we find that keychains containts sensitive data like passwords 
So lets crack it 

I found a tool on github "chainbreaker" to do that

Looks like we need another password

![image](https://github.com/NassimMansouri/writeups/assets/123596322/18a55609-ff62-402b-a2ee-d78a324148f4)

after a little searching we see in the family pics folder a sus watson picture 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/7fc56565-0063-4ba4-886e-d9fbc44ed1ac)

looks like we found it

![image](https://github.com/NassimMansouri/writeups/assets/123596322/58a246c8-2e99-4f8f-9618-f9c2073a751a)

going back to cracking the keychain 

![image](https://github.com/NassimMansouri/writeups/assets/123596322/61bdfd5b-5344-426f-8e78-520c7f1f9466)

and we get the second part 

shellmates{NaV1gAT3_tH3_unS33n_WHEre_F1l3$_gAThEr_T0_c0nv3Ne}

