## sscli
Secret Server Command-Line Interface

This utility uses the Thycotic Secret Server Web Service API to provide a command-line interface to create, edit, delete, and read your Secret Server resources.
### To Install Dependencies
```
virtualenv ./venv-sscli
. ./venv-sscli/bin/activate
pip install -r requirements.txt
```

### Set-up your credentials
Your org ID is visible in the bottom right corner when you log into https://secretserveronline.com
```
export SECRET_SERVER_ORG=1234
export SECRET_SERVER_USERNAME=yourusername
export SECRET_SERVER_PASSWORD=yourpassword
```

### List all your folders
#####Command
```
./sscli get folder
```
#####Output
```
Development
Staging
Production
Office
Vendors
```

### Example Commands
All search commands in Secret Server are fuzzy (case-insensitive, partial matches allowed).

### Search for a specific folder
#####Command
```
./sscli get folder prod
```
#####Output
```
Production
```

### Search and display secret details
#####Command
```
./sscli get secret party service
```
#####Output
```
Secret Name: Some 3rd party Service API Credential
Resource: AKBB7VKDFYLBBTEAJ5A
Username: sample_user
Password: 12345678abcdefg

Secret Name: 3rd party Service Web Credential
Resource: https://example.com
Username: yourname@example.com
Password: 12345678abcdefg
Notes: This is a 3rd party service we subscribe to.
```
