# SHH-Connection-

# STEP5a: Install ssh in Termux
- Refer to the following page for more info
```
https://wiki.termux.com/wiki/Remote_Access
```
- Open Termux & execute the following commands:
```
$ apt update && apt upgrade
- On first prompt, enter Y. On second and third prompt, just press Enter.
$ pkg install busybox termux-services
- After installation you need to restart session or source this file:
''source $PREFIX/etc/profile.d/start-services''
$ sv-enable ftpd
sv up ftpd
- FTP server will run on port 8021 in read-only mode.
If you need to stop server, run $ sv down ftpd.
$ pkg install openssh
- On prompt, enter Y.
$ sshd
- If you need to stop `sshd`, just kill it's process:
$ pkill sshd
$ passwd
$ whoami
- Take note of the username. Example: u0_a290
$ ifconfig
- Take note of the IP address beside inet. Example: 192.168.1.51
```

# STEP5b: Connecting to Android via SSH
- To connect from Windows Gitbash to your Android, we need to setup proper ssh keys.
- This involves copying your Windows ssh keys to Android.
- On Windows terminal such as Git bash:
```
$ ssh-keygen -t rsa -b 2048 -f id_rsa
$ cd ~/.ssh
$ ls -la id_rsa*
$ ssh-copy-id -p 8022 -i id_rsa u0_a290@192.168.1.51
```

- Sample Output from Windows GitBash.
```
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "id_rsa.pub"
The authenticity of host '[192.168.1.125]:8022 ([192.168.1.125]:8022)' can't be established.
ED25519 key fingerprint is SHA256:RAhKshLsEEQQlocGYP38RCQXJIDgETCOCrGJ7PxVFPg.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
u0_a257@192.168.1.125's password:

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh -p '8022' 'u0_a257@192.168.1.125'"
and check to make sure that only the key(s) you wanted were added.
```

- You can now test ssh connection. Make sure to use the exact user and IP address
```
$ ssh -p 8022 u0_a290@192.168.1.51
```

- To connect to the Android Termux via Putty
- Make sure to indicate SSH port 8022

 <h3 align="left">Support:</h3>
<p><a href="https://www.buymeacoffee.com/Darkwebdisclaimer "> <img align="left" src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="50" width="210" alt="Darkwebdisclaimer " /></a><a href="https://ko-fi.com/Darkwebdisclaimer "> <img align="left" src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3" height="50" width="210" alt="Darkwebdisclaimer " /></a></p><br><br>

<p><img align="left" src="https://github-readme-stats.vercel.app/api/top-langs?username=darkwebdisclaimer&show_icons=true&locale=en&layout=compact" alt="darkwebdisclaimer" /></p>

<p>&nbsp;<img align="center" src="https://github-readme-stats.vercel.app/api?username=darkwebdisclaimer&show_icons=true&locale=en" alt="darkwebdisclaimer" /></p>

<p><img align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=darkwebdisclaimer&" alt="darkwebdisclaimer" /></p>

