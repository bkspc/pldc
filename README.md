# root access without serial port and disable ethernet isolation

First its not AP isolation, wifi clients can communicate just fine. its just ethernet being isolated.

1. 192.168.1.1 use f~i!b@e#r$h%o^m*esuperadmin account, enable telnet
2. connect putty(telent) to 192.168.1.1 port 23, login(user/pw) gepon/gepon, enable /gepon, ddd (enter), shell (enter) should show `Please use port 26 to telnet`
3. connect putty(telnet) to 192.168.1.1 port 26, login root/GEPON (if wrong then crack it else use serial port)
    using vi text editor `:w`=save,`:q`=quit,`o`=open and put text in a new line below current line until (Esc) hit,`i`=insert text before cursor until (Esc) hit
4. `vi /fh/extend/pldc`, press `i` and copy script below, right click to paste in putty.

    to save and exit, (Esc)`:wq`
    and make it executable `chmod +x /fh/extend/pldc`

5. `vi /fh/extend/initialize.sh` type `:/watchdog` (enter), o, type `pldc &`,(Esc) `:wq` (pldc will be our custom script)
    [should look like this](https://user-images.githubusercontent.com/46971040/60866272-70af6080-a217-11e9-8090-8d99dbed8a68.png)

I would recommend change the root password `passwd root`, in case you open in firewall

Created by [@chudyvf](https://github.com/chudyvf) [origin](https://gist.github.com/kbeflo/de3b1610b1879f8e92966ba106f83f97#gistcomment-2965179)