# password_check_vuln

The purpose of this program is to allow individuals to check whether or not a password has been hacked to help in determining if the individual might want to use the password for an account.

Made with Python version 3.9.1

**IMPORTANT: To ensure no issues, use Python 3.9.1 or newer.
This is intended for personal use only.**

NOTICE: Do not use this project maliciously, it can be used to let individuals know if a password, that one might potentially use for an account, has been compromised through https://haveibeenpwned.com/API/v2

# Installation/Setup

If you know how, get the files into a folder, make it a virtual environment, and install dependencies using requirements.txt.

Otherwise: 

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

# Usage
Assuming everything you get everything installed and setup correctly, whether through Pycharm or other means necessary, you may now use the program through the terminal along with a file that has passwords you want to test.

#### Step 1:
Make a text document and each line containing one password.

*For example* the document may look like:
```sh
password123
passon11
mypass123
mySuperSecure$password(^
```
**Note:** this passwords text document should have a **file extension of *.txt*** to avoid issues. Also, make sure this passwords document is in the same folder as the everything else.

Now with everything in place,
in the terminal or command prompt:
```sh
$ python3 checkmypass.py <passwords_doc>
```
or, as an example assume I have a passwords text document named ***passes.txt*** I would enter:
```sh
$ python3 checkmypass.py passes.txt
```
and the output, assuming passes.txt has content of 
```sh
password123
passon11
mypass123
mySuperSecure$password(^
```
would be,

output:
```sh
CBFDA C6008F9CAB4083784CBD1874F76618D2A97
password123 was found 126927 times... you should probably change your password.
E776E E55472637FCC76EFBC430118601FE1693CE
passon11 was found 8 times... you should probably change your password.
D2BF0 2E60ED38AF96751C5A78A8FFBE32F4598F9
mypass123 was found 2967 times... you should probably change your password.
14307 B1B7A404DBB4DD96819323CCDD4BE44F16C
mySuperSecure$password(^ was NOT found. Carry on!
```
The output represents how many time the password has been hacked, or not.
This uses the sha1 to produce the long string of character right before showing how many time the password (if applicable) was hacked/found.


# Why
Because with this program, instead of using the same site where it could calculate the password and spits out whether or not it has been hacked/found (through the internet), this allows only the first five characters of the hashed password to go through the internet, and then bring back the results of all matching Sha1 hashes (which could be thousands due to it gathering all first five hashed character matches) but through some code using the remaining hashed characters of a password, the program compares the full hash to the hashes (hundreds/thousands) that started with those first five character in the digest.

This avoids sending valuable information across the internet that could be captured and used for malicious purposes.

This also allows people to test passwords that they might use for an account.
