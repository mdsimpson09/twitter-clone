Twitter-Clone- "Tweeter" 

### Prerequisites

- Python 3.x
- Flask
- WTForms 

Step-by-step instructions on getting a dev environment running.
1. copy repository from github 
2. open terminal and navigate to the project directory
3. pip install -r requirements.txt
4. python3 -m venv venv
5. run venv/bin/activate 
6. set up local db "createdb warbler" and "python seed.py"
7. run command "flask run" to start the server

Important Note:
If you are using Python 3.8 instead of 3.7, then you will have issues with installing some of the packages in the requirements.txt file into your virtual environment. For Python 3.8 students, we recommend deleting psycopg2-binary from the requirements.txt file, and using pip install psycopg2-binary in the terminal in order to successfully install this package. 

if issues with email_validator 

This error is occurring because the safe_str_cmp function was removed from Werkzeug in version 2.0

The flask_wtf package you are using likely has not been updated to support Werkzeug 2.0 yet, so it is still trying to import the old safe_str_cmp function.

A few things you could try:

1. Downgrade Werkzeug to version 1.x by running pip install werkzeug==1.0.1

2. Try upgrading flask_wtf to the latest version in case support for Werkzeug 2.0 was added: pip install --upgrade flask-wtf      *****

3. If upgrading flask_wtf doesn't help, you may need to downgrade it as well to match your Werkzeug version: pip install flask-wtf==0.14.3

As a last resort, you could try patching flask_wtf yourself to remove the import of safe_str_cmp.
