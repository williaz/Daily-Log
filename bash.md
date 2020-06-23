- [x] [add execute permission](https://askubuntu.com/questions/409025/permission-denied-when-running-sh-scripts)
```bash
cd /path/to/target
chmod +x the_file_name
```
- [x] [copy files between servers](https://stackoverflow.com/questions/11208895/bash-command-to-copy-file-from-one-computer-to-another)
```bash
scp user@host:/path/file .
scp file user@host:/path
```
- [x] [check disk free](https://unix.stackexchange.com/questions/218613/using-df-h-i-need-to-create-an-bash-script-that-displays-anything-about-60-ut)
```bash
df -h .
```
- [x] zip
```bash
tar -zcvf ${dest.file.tar.gz} targ.dr
tar -zxvf ${file.tar.gz}
```
- [x] count line
```bash
wc -l file
```
- [x] read 110th line
```bash
sed -n 110p file
```
- [x] add rsa key for bitbucket
```bash
eval ${ssh-agent -s}
ssh-keygen -t tsa -b ${num} -C "${email}"
```
