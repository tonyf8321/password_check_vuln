# password_check_vuln

The purpose of this program is to allow individuals to check whether or not a password has been hacked to help in determining if the individual might want to use the password for an account.

Made with Python version 3.9.1

**IMPORTANT: To ensure no issues, use Python 3.9.1 or newer.
This is intended for personal use only.**

NOTICE: Do not use this project maliciously, it can be used to let individuals know if a password, that one might potentially use for an account, has been compromised through https://haveibeenpwned.com/API/v2

# Installation/Setup

#### Step 1: 
Get all of the files in a separate folder on your machine.

#### Step 2: 
Make the folder you have stored only the files obtained from this project a virtual envrionment.

From the command prompt for windows users:

```sh
$ python3 -m venv <path_folder_whereof_files>
```
or
>try using 
py to replace python3 depending on the alias that is on the machine.

From the terminal:
```sh
$ python3 -m venv <path_folder_whereof_files>
```
or
>try using python or py to replace python3 depending on the alias that is on the machine.

#### Step 3: 
Activate the virtual environment.
Replace venv with the folder like in the previous steps that use <path_folder_whereof_files>
```sh
$ ./<venv>/Scripts/activate
```
After you enter that correctly, you will notice added text besides the command line name, reading the virtual environment name, which should be the folder name if you've followed the steps.

#### Step 4: 
Install dependencies.
Using the *requirements.txt* file, install the dependencies listed.
Try the following command while in the folder:
```sh
(<venv>)$ pip3 install -r requirements.txt
```
Note: you may use pip as long as it uses python3.

