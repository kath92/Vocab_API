# Vocab_API

A simple endpoint to display the vocabulary of my English students (as well as my French vocabulary) which will be consumed by my front-end site.

At the moment, the front-end is written in Vanilla JS, however I am planning to use React in near future.

Vocabulary for this API is in its initial phase (before thorough proofreading) and was created by my simple Python script that extracted word-translation pairs to a csv format which then wass loaded to Django using yet another script.

## To Deploy:

1) Install requirements.txt.
2) Go to the terminal in project folder `vocab_api` and use:
      `python manage.py runmigrations`
3) Run the server:
      `python manage.py runserver`

It runs on `http://localhost:8000/api/`

To use the API by your website, go to settings.py and ensure that CORS_ORIGIN_ALLOW_ALL is set to True. Yiou can also set it to False and allow your port in line with CORS_ORIGIN_WHITELIST.

To change the vocabulary pairs served by this API, go to `vocab_api/scripts/initial_load.py` where you need to uncomment lines with all().delete() and put your own information into VOCAB_LIST, CATS and NAMES that corresponds to csv files you wish to load. Remember to uncomment delete so that script runs through the whole list of your vocabulary file names.
