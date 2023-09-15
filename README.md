
# iBioML

Our main research area is pattern recognition in bioinformatics, especially, biological motif analysis. We developed various bioinformatics tools online.

## Installation

To set up the project locally, follow these steps:

Clone the repository:


   ```bash
   git clone https://github.com/K-Tech22/iBioML.git
   ```
Create a virtual environment and activate it:
   ```bash
    python -m venv myenv
    source myenv/bin/activate
   cd biotechwebsite
 
```
Install the required dependencies using pip:
   ```bash
    pip install -r requirements.txt
   ```
Apply the database migrations:
   ```bash 
    python manage.py makemigrations    
    python manage.py migrate
   ```
Start the development server:

   ```bash
python manage.py runserver
   ```
The development server will be accessible at http://localhost:8000/.

# Set up for email invitation as sender

Navigate to the project folder

```bash
cd iBioML/biotechwebsite/biotechwebsite
```

Create '.env' File:

```bash
touch .env
```

Open the '.env' file
```bash
nano .env
```

Add Necessary Environment Variable:
```bash
EMAIL_HOST_USER=Put Sender Email
EMAIL_HOST_PASSWORD=Put google App paasswords
```
Resource for google App passwords:
[Google app passwords](https://support.google.com/accounts/answer/185833?hl=en)

# Google OAuth Configure

Head over to [Google Developer APIs Console](https://console.developers.google.com/apis) and create a new project

![create-g-oauth-project](./images/create-g-oauth-project.jpg)

Then, register your app by filling the [OAuth consent screen](https://console.developers.google.com/apis/credentials/consent)

![create-oauth-project](./images/g-oauth-consent-screen-1.jpg)

Then, create a new __OAuth client ID__ under [Credentials](https://console.developers.google.com/apis/credentials)
Select __Web application__ for the __Application type__.

Then, add:

* http://127.0.0.1:8000 under __Authorized JavaScript origin__
* https://127.0.0.1:8000/google/login/callback/ under __Authorized redirect URIs__

![create-oauth-project](./images/clientID.jpeg)

After a successful Oauth client ID creation, copy your client ID and your client secret

Open http://127.0.0.1:8000/admin and login to Django Admin. Under sites click add and put 127.0.0.1:8000 as both the
__Domain name__ and __Display name__
![create-oauth-project](./images/create-dj-site.jpg)

Then, under Social Application click Add and fill in the details as follows:

1. Provider: Google
2. Name: Oauth app
3. client_id: <The client ID you created>
4. Secret Key: <The secrete Key you created>
5. Sites:127.0.01:8000

![create-oauth-project](./images/add-social-app.jpg)
