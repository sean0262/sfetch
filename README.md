# sfetch
light-weight system information script written in less than 20 lines. 

![sfetch](https://i.imgur.com/tjlk8kh.png)



Method 1.  
`cd /usr/bin/`  
`sudo git clone https://github.com/sean0262/sfetch.git`  
Method 2.  
`cd /usr/bin/`  
`sudo nano sfetch`  
copy the following:  
>#!/bin/bash  
>  
>distro=$(cat /etc/os-release | head -1 | sed 's/"//g' | cut -d= -f2)  
>kernel=$(uname -r)  
>shell=$(echo `$SHELL --version` | cut -d'(' -f1)  
>uptime=$(uptime -p)  
>packages=$(dpkg-query -W | wc -l)  
>de=$(echo "$XDG_CURRENT_DESKTOP")  
>session=$(echo "$GDMSESSION")  
>memory=$(free -hm | awk 'NR==2{printf "%s/%s\n", $3,$2}')  
>  
>echo "OS: $distro"  
>echo "Kernel: $kernel"  
>echo "Shell: $shell"  
>echo "Uptime: $uptime"  
>echo "Packages: $packages"  
>echo "DE: $de"  
>echo "Session: $session"  
>echo "Memory: $memory"`  
`paste it into the sfetch file, ctrl+shift+v`  
save the file by doing the following:   
`ctrl+x then when asked to save modified buffer press y and then press enter.`  
`sudo chmod 755 sfetch`  
  

<i>If you are using something besides bash, change the first line to: `#!/bin/YOUR-SHELL-HERE`</i>
