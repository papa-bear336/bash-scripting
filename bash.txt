#!/bin/bash

################################################################################################
#        Author: Willis Briggs (will@willisbriggs.me)                                          #
#	 Date Created: Years Ago                                                               #
#                                                                                              #
################################################################################################
#	 8""""8                        8""""8                                                  #
#	 8    8   eeeee eeeee e   e    8    8 e     e  eeeee eeeee eeee eeeee                  #
#	 8eeee8ee 8   8 8   " 8   8    8eeee8 8     8  8   8 8   " 8    8   "                  #
#	 88     8 8eee8 8eeee 8eee8    88   8 8e    8e 8eee8 8eeee 8eee 8eeee                  #
#	 88     8 88  8    88 88  8    88   8 88    88 88  8    88 88      88                  #
#	 88eeeee8 88  8 8ee88 88  8    88   8 88eee 88 88  8 8ee88 88ee 8ee88                  #
################################################################################################

### Variables Section ###
alias='vscode=./flatpak run com.visualstudio.code $1'









### ARCH SECTION ###
alias maskbacklight='sudo systemctl mask systemd-backlight.service'


### DEBIAN / UBUNTU DISTRIBUTION SECTION ### 

## APT Specific
alias fixit='sudo apt --fix-broken install'
alias update='sudo apt update'
alias clean='update && sudo apt autoclean'
alias remove='update && sudo apt autoremove'
alias upgrade='update && sudo apt upgrade -y'
alias upgrade-distro='sudo do-release-upgrade'
alias show-upgrade='sudo apt list --upgradable'
alias do-upgrade='sudo apt upgrade -y'

## SNAP Specific 
alias snap-remove='remove-snap'
alias snap-remove-all='config-remove'
alias snap-list='snap list'


### RASPBERRY PI/OS SECTION ###
alias cantsee='xhost +local: &&'
alias raspfirm='sudo rpi-update'
alias raspconf='sudo raspi-config'


### DISTRO INDEPENDENT ###

## APPLICATION / SERVICE(S) SECTION 

# BASH Specific
alias editbash='bash2txt'
alias editbashnow='sudo nvim ~/.bash_aliases'
alias bashit='update-bash'
alias bash2txt='cat ~/.bash_aliases > bash.txt && flatpak run com.visualstudio.code bash.txt'
alias update-bash='mv ~/bash.txt ~/.my_dot_files/Configurations/BASH/.bash_aliases && source ~/.bashrc; echo Bash Update!'
alias bashinstall='sudo ln -s ~/.my_dot_files/.bash_aliases ~/.bash_aliases'
alias alias-search='cat ~/.bash_aliases | grep $1'

# Miscellaneous 
alias showdisk='sudo fdisk -l'
alias ip-add='curl ifconfig.me'
alias all='ls -la'
alias whereamI='pwd'
alias chess='telnet -r freechess.org 5000'
alias ver='lsb_release -a'
alias ddstatus='sudo kill -USR1 $(pgrep ^dd)'
alias disku='sudo du -sh * | sort -rn | head'
alias usedips='nmap -sP 192.168.1.0/24 > used_ips.txt'
alias link='sudo ln -s'
alias locate-update='sudo updatedb'
alias spaceleft='df -h'
alias howmuch='spaceleft'
alias rmdir='rm -rf'
alias dotfiles='cd ~/.my_dot_files/; echo Your Dot Files'
alias show-last='tail -n 1'
alias top='btm'
alias htop='btm'
alias vim='nvim'
alias vi='nvim'
alias ports-open='sudo ss -tulpn'
alias listening='ports-open'
alias whatsopen='ports-open'
alias openports='whatsopen'
alias permissions='stat --format=%a'
alias perms='permissions'
alias userown='sudo chown -R $USER:USER'
alias mkdir='mkdir -p'
alias ls='ls -la'

# Docker Specific
alias docker-stop-all='docker container stop $(docker container ls -aq)'
alias docker-start-all='docker container start $(docker container ls -aq)'
alias docker-nuke='docker container stop $(docker container ls -aq) && docker container prune'
alias docker-prune='docker container prune'
alias enter-container='container-enter'

# Emacs Specific
alias terminal-emacs='emacs -Q -nw'
alias emacs-terminal='terminal-emacs'

# Firewalld Specific 
alias fw-open-port='firewalld-port'

# IP Address Specific 
alias ip-tailscale='tailscale-ip'
alias my-ip='ip address | grep enp'

# NMAP Specific
alias nmap-install='sudo apt install nmap'
alias nmap-network='nmap -sP 192.168.1.0/24'
alias nmap-os='sudo nmap -sT -O 192.168.1.0/24'
alias nmap-os-file='sudo nmap -sT -O 192.168.1.0/24 > nmap_output'

# Samba Specific
alias samba-choice='sys-d-choice'

# Transmission-Daemon Specific 
alias trans-choice='sys-d-choice'
alias trans-settings='trans-d-settings'

# Update MOTD Login Message
alias install-message='sudo ln -s ~/.my_dot_files/MOTD/98-my-message /etc/update-motd.d/98-my-message'
alias update-motd='sudo nvim /etc/update-motd.d/98-my-message'
alias update-message='update-motd'
alias edit-message='update-message'
alias test-message='sudo run-parts /etc/update-motd.d/'

# SYSTEMCTL Specific 
alias system-input='sys-d'
alias system-choice='sys-d-choice'
alias daemon-reload='sys-d-choice'
alias reload-daemon='sys-d-choice'

### SYSTEM / SESSION(S) SECTION ###

## Power / Reboot / Session
alias poweroff='sudo /sbin/poweroff'
alias reboot='sudo /sbin/reboot'
alias shutdown='sudo /sbin/shutdown -h now'

## SSH Key Generation / Management 
alias make-key='make-ss-k'
alias copy-key='copy-ss-k'
alias edit-auth='nvim ~/.ssh/authorized_keys'

## Port-forwarding Section
alias tailscale-ip='ip address | grep tailscale0'
alias p-forward='port-forward-choice'

### INSTALLATION SECTION ###
alias install-tailscale='curl -fsSL https://tailscale.com/install.sh | sh'
alias install-pi-hole='curl -sSL https://install.pi-hole.net | bash'
alias install-docker-arch='sudo pacman -S docker.io'
alias install-docker-ubuntu='sudo apt install docker.io'
alias install-docker-script='curl -fsSL https://get.docker.com -o get-docker.sh'
alias install-casaos='curl -fsSL https://get.casaos.io | sudo bash'
alias install-flathub='flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo'
alias install-paru='sudo pacman -S --needed base-devel git -y && git clone https://aur.archlinux.org/paru.git && cd ~/paru && makepkg -si'
alias install-btm-arm='curl -LO https://github.com/ClementTsang/bottom/releases/download/0.9.6/bottom_0.9.6_arm64.deb && sudo dpkg -i botm_0.9.6_arm64.deb'
alias install-btm-x86='curl -LO https://github.com/ClementTsang/bottom/releases/download/0.9.6/bottom_0.9.6_amd64.deb && sudo dpkg -i bottom_0.9.6_amd64.deb'
alias install-btm-ubuntu='install-btm-x86'
alias install-btm-raspberrypi='install-btm-arm'
alias install-leaktest='curl https://raw.githubusercontent.com/macvk/dnsleaktest/master/dnsleaktest.sh -o dnsleaktest.sh && sudo chmod +x dnsleaktest.sh'
alias install-nmap='nmap-install'
alias install-bash='bash-install'

###### FUNCTION SECTION ###### ( Edit with caution )

# Make SSH-Key
make-ss-k () {
   echo "Filename?"
   read f_name
   ssh-keygen -b 4096 -f ~/.ssh/$f_name
}
export -f make-ss-k

# Copy Particular SSH Key
copy-ss-k () {
   echo "Filename?"
   read "file_name"
   echo "user@host?"
   read "host_loc"
   ssh-copy-id -i ~/.ssh/$file_name.pub $host_loc
}
export -f copy-ss-k

# Listening Ports of Specified App (checked by ChatGPT) 
app-ports () {
    echo "Which app to listen to?"
    read which_app
    sudo ss -tulpn | grep "$which_app"
}
export -f app-ports

# Open Ports on FirewallD
firewalld-port () {
    echo "Which port?"
    read "fw_port"
    echo "Which Zone?"
    read "fw_zone"
    sudo firewall-cmd --zone=$fw_zone --permanent --add-port=$fw_port/tcp
}
export -f firewalld-port

# Port Forward w/ Prompt (checked by ChatGPT) 
port-forward () {
    echo "user@host?"
    read which_loc
    echo "local port?"
    read local_port
    echo "remote port?"
    read remote_port
    loc="ssh $which_loc -L $local_port:localhost:$remote_port"
    $loc
}
export -f port-forward

# To Completely Remove a SNAP & its' configurations
remove-snap () {
    sudo snap list &&
    echo "Which Snap to remove?"
    read "which_snap"
    sudo snap remove $which_snap --purge
}
export -f remove-snap

# To Remove Lingering Snap Configs
config-remove () {
    sudo snap saved &&
    echo "Which one?"
    read "which_one"
    sudo snap forget $which_one
}
export -f config-remove

# Prompt two Enter The Correct Container via Docker
container-enter () {
    docker ps &&
    echo "Container Name?"
    read c_name
    docker exec -it $c_name sh 
}
export -f container-enter

# Transmission-Daemon Edit Settings Option
trans-d-settings () {
    echo "Edit which location:"
    echo "1. system"
    echo "2. userland"
    echo "3. watch"

    read -p "Enter your choice: " choice

case $choice in
    1)
        sudo nvim /etc/transmission-daemon/settings.json
        # Add your Option 1 functionality here
        ;;
    2)
        sudo nvim /home/$USER/.config/transmission-daemon/settings.json
        # Add your Option 2 functionality here
        ;;
    3)
	sudo nvim /var/lib/transmission-daemon/.config/transmission-daemon/settings.json
	# Add your Option 3 fuctionality here
	;;

    *)
        echo "Invalid choice. Please choose again."
        ;;
esac
}
export -f trans-d-settings

# SYSTEMCTL State / Service Input Required
sys-d () {
    echo "start, stop, restart, enable, status"
    read "sys_state"
    echo "which service"
    read "which_serv"
    sudo systemctl $sys_state $which_serv
}
export -f sys-d

# SYSTEMCTL State / Service Choice
sys-d-choice () {
    echo "Which state"
    echo "1. start"
    echo "2. stop"
    echo "3. restart"
    echo "4. status"
    echo "5. daemon-reload"

    read -p "Enter your choice: " state


    echo "Which service"
    echo "A. firewalld"
    echo "B. networking"
    echo "C. openvpn"
    echo "D. samba"
    echo "E. transmission-daemon"
    echo "F. daemon-reload"

    read -p "Enter your choice: " service

case $state in
    1)
        state=start
        # Add your Option 1 functionality here
        ;;
    2)
        state=stop
        # Add your Option 2 functionality here
        ;;
    3)
	state=restart
	# Add your option 3 functionality here
	;;
    4)	state=status
	# Add your option 4 fuctionality here
	;;
    5)
	state=daemon-reload
        ;;
    *)
        echo "Invalid choice. Please choose again."
        ;;
esac
case $service in
    A)
        service=firewalld
        # Add your Option A functionality here
        ;;
    B)
        service=networking
        # Add your Option B functionality here
        ;;
    C)
        service=openvpn
        # Add your option C functionality here
        ;;
    D)
        service=smbd
        # Add your option D fuctionality here
        ;;
    E)
	service=transmission-daemon
	# Add your option E functionality here
        ;;
    F)
	service=$null
	;;
    *)
        echo "Invalid choice. Please choose again."
        ;;
esac
	sudo systemctl $state $service
}
export -f sys-d-choice

# Port-Forwarding Choice
port-forward-choice () {
    echo "Which server:"
    echo "1. File-Server"
    echo "2. TheBeastNode"
    echo "3. Plex-Server - TS"

    read -p "Enter your choice: " choice

case $choice in
    1)
        ssh papa_bear336@192.168.1.150 -L 18384:localhost:8384
        # Add your Option 1 functionality here
        ;;
    2)
        ssh papa_bear336@192.168.1.250 -L 28384:localhost:8384
        # Add your Option 2 functionality here
        ;;
    3)
        ssh dgwolfnc@100.99.37.3 -L 38384:localhost:8384 
        # Add your Option 3 fuctionality here
        ;;

    *)
        echo "Invalid choice. Please choose again."
        ;;
esac
}
export -f port-forward-choice

###### THE END OF THE FUNCTION SECTION

###### BASH PROMPT SECTION ###### (edit with caution )

export PS1="\[$(tput bold)\]\[$(tput setaf 7)\][\[$(tput setaf 4)\] \V\[$(tput setaf 7)\] ] [\[$(tput setaf 4)\] \u\[$(tput setaf 7)\] @ \[$(tput setaf 4)\]\h \[$(tput setaf 7)\]] [ \[$(tput setaf 4)\]\w \[$(tput setaf 7)\]] \n[\[$(tput setaf 4)\]\\$\[$(tput setaf 7)\]] \[$(tput sgr0)\]"

###### THE END OF THE BASH PROMPT SECTION
