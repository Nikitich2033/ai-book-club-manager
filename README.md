# Team Sigma
Software Engineering Group Project Year 2 - "Book Clubs"

## Contents on this page:
- [Project Deployment](#Project-deployment)
- [Video Tutorial](#Video-tutorial)
- [Project Structure](#Project-structure)
- [Intallation instructions](#Installation-instructions)
- [Team Sigma Members](#Members)
- [Sources used for webapp](#Sources)


**WARNING**: Due to Heroku free deployment the RAM limitations could sometimes not handle the recommendation system; therefore would take some page refresing until it works.

**UPDATE**: The system is no longer deployed, due to Heroku limiting access to their free tier.

## Video tutorial
We have created a video link [here](https://www.youtube.com/watch?v=FDh0NJu4GA8) with a walkthrough of the website and how to navigate around it.

## Project structure
The project is called `system`.  It currently consists of a single app `book_club`. With the recommender system within a folder named `util` within the `book_club` app.

## Installation instructions
To install the software and use it in your local development environment, you must first set up and activate a local development environment.  From the root of the project:

```
$ virtualenv venv
$ source venv/bin/activate
```

Install all required packages:

```
$ pip3 install -r requirements.txt
```

Migrate the database:
```
$ python3 manage.py migrate --run-syncdb
```

Add cache to the database:
```
$ python3 manage.py createcachetable
```

Seed the development database with (due to seeding from CSVs will take around 5-7 minutes to seed):

```
$ python3 manage.py seed
```

Before running tests you must run the following commands:

```
$ python3 manage.py collectstatic
```

Run all tests with:
```
$ python3 manage.py test
```

Run the server with the following command:
```
$ python3 manage.py runserver
```

## Sources

- [Django filter](https://django-filter.readthedocs.io/en/stable/index.html) was used to inspire the use of filters (see book_club.filters.py) for models within the Django application.
- [AI Recommender System Training](https://www.linkedin.com/learning/building-recommender-systems-with-machine-learning-and-ai/recommender-engine-walkthrough-part-1)
