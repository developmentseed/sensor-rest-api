
A REST API for DustDuino air quality sensors

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

For API documentation [click here](http://api.opendustmap.com).

## Deployment to Heroku

Use the heroku button above or manually create an app on heroku and deploy. For configuration purposes, the following table maps environment variables to their Django setting:

|Environment Variable                    |Django Setting              |Development Default          |Production Default
| -------------------------------------- | -------------------------- | --------------------------- | -----------------
|DJANGO_SECRET_KEY                       |SECRET_KEY                  |CHANGEME!!!                                    |raises error
|DJANGO_PORTAL_URL                       |PORTAL_URL                  |http://127.0.0.1:8000                                    |http://127.0.0.1:8000

## Installation on local machine

Create a virtual environment
```
virtualenv venv
source venv/bin/activate
```

Install the requirements
```
pip install -r requirements.txt
```

Initialize the database
```
python sensor_rest_api/manage.py syncdb
```

Start the server
```
python sensor_rest_api/manage.py runserver
```
## Docs Deployment

This project is set up with [Travis](https://travis-ci.org/) deploy scripts already included which will deploy documentation to `gh-pages`. To utilize these, you will need to enable the repo on the Travis system and include the following two environment variables.

- **GH_REF** - the URL of the repo, similar to `github.com/developmentseed/dustduino-server.git`
- **GH_TOKEN** - a GitHub personal access token available from https://github.com/settings/tokens