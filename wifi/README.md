sudo apt update && sudo apt install bc module-assistant build-essential dkms git

git clone rtl8821ce

#need to remove rtl8821ce-dkms driver if it is present

sudo apt remove rtl8821ce-dkms

#Get in the directory of downloaded rtl8821ce

cd rtl8821ce

#while in rtl8821ce directory

sudo m-a prepare

#try again if the output has Couldn't create the /usr/src/linux symlink!  while in rtl8821ce directory

 sudo ./dkms-install.sh

#open a new terminal

sudo nano /etc/modprobe.d/blacklist.conf

#add to the end and save

blacklist rtw88_8821ce

#the system needs to shutdown and it was advised to wait for few minutes before booting again so that the changes will apply

current info about my system:

lsmod | grep 8821
8821ce               2060288  0
cfg80211              974848  1 8821ce

dkms status
rtl8821ce/v5.5.2_34066.20200325, 5.15.0-69-generic, x86_64: installed
