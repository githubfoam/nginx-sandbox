
# nginx sandbox
ubuntu-19.04,ubuntu-16.04
~~~~
>vagrant up vg-squid-01
>vagrant ssh vg-squid-01
vagrant@vg-squid-01:~$ curl http://192.168.2.11 # nginx page OK

browse
http://192.168.2.11 # nginx page OK
http://192.168.2.11:84 # not OK!
~~~~
centos-8.0
~~~~
$ nginx -v
nginx version: nginx/1.14.1

curl http://192.168.2.9  # nginx page
curl http://192.168.2.9:85  # not nginx page

[vagrant@vg-squid-02 ~]$ cat <<EOF | sudo tee /usr/share/nginx/html/index.html
hello nginx starter page
EOF
hello nginx starter page

[vagrant@vg-squid-02 ~]$ curl http://192.168.2.9
hello nginx starter page

browse
http://192.168.2.9  # custom nginx page
http://192.168.2.9:85  # not nginx page

~~~~

centos-7.7
~~~~
>vagrant up vg-squid-02
>vagrant ssh vg-squid-02
$ nginx -v
nginx version: nginx/1.16.1
$ curl http://192.168.2.9  # not nginx page

browse
http://192.168.2.9  # not nginx page
http://192.168.2.9:85  # not nginx page

[vagrant@vg-squid-02 ~]$ sudo rm /usr/share/nginx/html/index.html
[vagrant@vg-squid-02 ~]$ cat <<EOF | sudo tee /usr/share/nginx/html/index.html
hello nginx starter page
EOF
hello nginx starter page

[vagrant@vg-squid-02 ~]$ curl http://192.168.2.9
hello nginx starter page

browse
http://192.168.2.9  # custom nginx page
http://192.168.2.9:85  # not nginx page

~~~~
