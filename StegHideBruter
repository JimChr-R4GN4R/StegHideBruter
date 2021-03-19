import subprocess
import argparse


logo = r"""
 _____ _             _   _ _     _     ______            _            
/  ___| |           | | | (_)   | |    | ___ \          | |           
\ `--.| |_ ___  __ _| |_| |_  __| | ___| |_/ /_ __ _   _| |_ ___ _ __ 
 `--. \ __/ _ \/ _` |  _  | |/ _` |/ _ \ ___ \ '__| | | | __/ _ \ '__|
/\__/ / ||  __/ (_| | | | | | (_| |  __/ |_/ / |  | |_| | ||  __/ |   
\____/ \__\___|\__, \_| |_/_|\__,_|\___\____/|_|   \__,_|\__\___|_| V1.0
                __/ |                                                 
               |___/  Coded by R4GN4R
"""
print(logo)

parser = argparse.ArgumentParser()
parser.add_argument( "-f", '--file', help="Target file", required=True , type=str )
parser.add_argument( "-l", '--list', help="Wordlist", required=True , type=argparse.FileType('rb') )
args = parser.parse_args()


pass_list = (args.list).readlines()
file = args.file

for cur_pass in pass_list:
	try:
		subprocess.run( 'steghide extract -sf '+ file +' -p ' + cur_pass.decode('utf-8'),shell=True, check=True, text=True)
		print("Correct Password:",cur_pass.decode('utf-8'))
		break # found correct key
	except UnicodeDecodeError:
		pass
	except:
		print("False Password:",cur_pass.decode('utf-8'))
		pass
