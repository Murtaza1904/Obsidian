
### crack station: 
https://crackstation.net/
Tell the hash algorithm and sometimes crack the password as well

### Hash identifier: 
https://hashes.com/en/decrypt/hash
Tell the hash algorithm and sometimes crack the password as well
It has both options: hash identify and hash decrypt
Use the password decrypt option as well

### Hash ID:
python3 hash-id.py
It tells only hash algorithm


### John the ripper

John the Ripper (JtR) is a free, open-source password security auditing and recovery tool. It comes preinstalled in Kali Linux.

| Hash Type         | --format=   |
| ----------------- | ----------- |
| **Windows NT**    | NT          |
| Windows LM        | LM          |
| **Linux SHA-512** | sha512crypt |
| **Linux MD5**     | md5crypt    |
| **MD5(raw)**      | Raw-MD5     |
| **SHA-1(raw)**    | Raw-SHA1    |
| **SHA-256(raw)**  | Raw-SHA256  |
NTLM format
```
Username:RID:LM_hash:NT_hash:::
```

hash start with aad has emtpy value in windows OS.
LM hash mostly return values in capital after cracking.

```
sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
```

```
john --format=raw-MD5 --wordlist=/usr/share/wordlists/rockyou.txt task1_md5_hashes.txt
```

```
john --rules=all --format=NT --wordlist=/usr/share/wordlists/rockyou.txt task1_md5_hashes.txt
```

John rules:
--rules=best64
--rules=all

Zip 2 John

```
zip2john secret_zip.zip > zip_hash.txt
```

```
cat zip_hash.txt
```

```
john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt
```

Rar 2 John

```
rar2john secret_practice.rar > rar_hash.txt
```

```
john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt
```

Shadow 2 John

```
unshadow task4_passwd_v2.txt task4_shadow_v2.txt > unshadowed.txt
```

```
john --wordlist=small_list.txt unshadowed.txt
```

```
john --show unshadowed.txt
```


SSH 2 John

```
ssh2john practice_id_rsa > ssh_hash.txt
```

```
john --wordlist=/usr/share/wordlists/rockyou.txt ssh_hash.txt
```

PDF 2 John

```
pdf2john secret_pdf.pdf > pdf_hash.txt
```

```
john --wordlist=/usr/share/wordlists/rockyou.txt pdf_hash.txt
```

Office 2 John

```
office2john secret_office_v2.docx > office_hash.txt
```

```
john --wordlist=/usr/share/wordlists/rockyou.txt office_hash.txt
```




In local machine, login password saved in SAM file (Windows database) in an NTLM format (hash).
SAM file required root or administrator level permissions to open that file.
SAM file required special tools to open that file.

`hashdump` command in meterpeter to get hashes of that machine.
