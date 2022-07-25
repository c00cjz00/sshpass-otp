# sshpass-otp
### 安裝
```
# Download sshpass_otp and put it in /usr/bin/sshpass_otp
sudo wget https://github.com/c00cjz00/sshpass-otp/raw/main/sshpass_otp -O /usr/bin/sshpass_otp

# 安裝 oathtool
sudo apt-get update
sudo apt-get -y install oathtool

```

### 指令
```
mypwd_file = pwd.txt
otp_file = otp.sh
account = allen
server = t3-c4.nchc.org.tw
cmd = 'date; hostname;'
sshpass_otp -O MOTP -f ${pwd_file} -c ${otp_file} ssh -q ${account}@${server} bash -c "${cmd}"
```

### 範例 pwd.txt
```
1234
```

### 範例 otp.sh, 請先取得 otp金鑰
如F7CHPNX3OxxxxxxxxxxxxxxxxxxxxxxEWF2VMKPUKBH6Q
```
#!/bin/sh
oathtool --totp -b F7CHPNX3OxxxxxxxxxxxxxxxxxxxxxxEWF2VMKPUKBH6Q
```
