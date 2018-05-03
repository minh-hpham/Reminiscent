# About
An electron application to allow user get their personal gmails and train them to find which email was interested over the time.

## Need to develop: 
```
Parsing requested emails: The body (content) of the requested emails are in encoded format. The current code sometimes fails to find the body, therefore cannot decode the body. Both the Python and NodeJS codes have this issue
UI: emails are shown in the order in the json file. Therefore, the seen emails are still on the top of the email list. Also, user can't see which emails they liked before
Learn user’s feedback: the current learn mechanism is based on the senders and subjects. The next step is to learn from the email’s content. The text content can be found in the text/plain part of the email’s body
Scalability: The current UI fails to load more than 1000 emails. I propose the solution of loading only N emails every time the window is reload. This approach requires the caching of which emails have been seen. 
Database: data are saved in json files in the local storage. Reading and writing from json files will take linear time. Using database is highly appreciated, especially for NodeJS code to read and write data.
```

## The structure of this project is

```
.
|--app
|    |-- main.js
|    |-- package.json
|    |-- renderer.js
|    |
|    |-- pycalc 
|    |   |-- readmail.py
|    |   |-- parsemail.py
|    |   |-- modifymail.py
|    |   `-- loadmore.py
|    |
|    |-- assets
|    |   |-- credentials
|    |       |-- client_secret.json
|    |   |-- css
|    |   |-- icons
|    |   |-- images
|    |   `-- js
|    |
|    |-- templates 
|    |   |-- signin.html
|    |   |-- download.html
|    |   |-- processing.html
|    |   `-- email.html
|    |
|    |-- npm_requirements.txt
|    |-- python_requirements.txt
|    `-- README.md
`--venv
```

# Requirements
## To be installed by yourself
```
python 3.6
virtualenv #recommended
node and npm
client_secret.json: follow step 1 from this link: https://developers.google.com/gmail/api/quickstart/python to download the file to app/assets/credentials and named it client_secret.json 

```

## Update/Additions - install with scripts
```
# Recommended: Update within virtualenv

# for npm
sudo npm install --unsafe-perm=true --allow-root -r npm_requirements.txt
npm install # will install anything logged in package-log.json
# for python
pip install -r python_requirements
```

# Run
```
npm start

# if prefer global electron, one must first install
sudo npm install -g electron --unsafe-perm=true --allow-root
# then run using
electron .
```


