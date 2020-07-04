# Intro To Django

[Tryhackme Intro To Django](https://tryhackme.com/room/django)

```
Username: django-admin
Password: roottoor1212
```

### Task5

#1 Admin panel flag?
```
nmap results show a webserver on port 8000 on navigating there 
```
![Initially](./images/initial.png)

```
According to above page the host has not been added so I tried to ssh into the machine as ssh was also open in the machine according to the nmap scans
```

`ssh django-admin@<machine_ip>`

```
and then supply the above password I was succesfully inside as django-admin
```

![](./images/ssh.png)
```
listing all directories I was able to see a messagebox directory cd messagebox/ and then again cd to messagebox here I found the seetings.py file
as from above article it was clear how to solve the problem
```

![](./images/settings.png)
```
nano settings.py and add the machine ip in the place of 127.0.0.1 and save the file now on accessing the website again
```
![](./images/page.png)

```
Nothing seemed interesting here so I decided to navigate to /admin section there on entering the above username password I got an error message
so I decided to create a new superuser
```
`python3 manage.py createsuperuser`

**you should be in the directory where manage.py is present**

![](./images/superuser.png)

```
Now acessing the admin section I was able to log in on searching a bit I found the first flag
Below that I also saw another user whose password was present in the pastebin
```
![](./images/strangeFox.png)

[CrackStation](https://crackstation.net/)
``` 
Taking that password hash and cracking it in crackstation I got the password. then on switching user I was now StrangeFox
```
![](./images/strangeFoxacc.png)



#2  User flag? 
```
on strange fox's home directory I could find the user.txt flag
```

#3 Hidden Flag ?
```
on some searching I found the third flag in /messagebox/messagebox/home.html
```
 