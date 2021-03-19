# StegHideBruter
This is a script that you can use to try many passwords with steghide and find the correct one to get the secret file from a stego image.

## Instructions
```
sudo apt-get install steghide
python3 sol.py -f <file> -l <wordlist_file>
example: python3 sol.py -f picture.bmp -l rockyou.txt
```
