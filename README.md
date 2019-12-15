# django-heroku-template

A template for Django projects hosted by Heroku


## Requirements

* [Heroku account](https://signup.heroku.com/)
* [Heroku command-line interface](https://devcenter.heroku.com/articles/heroku-cli)


## Getting started

Create your own repo using this template. Clone it to a local virtual environment.

Install the dependencies.

    $ pipenv install --dev

Create a local version of the database.

    $ python manage.py migrate

Do whatever Django things you want to do to configure your project. Then create an application with Heroku.

    $ heroku create your-app-name
    Creating ⬢ your-app-name... done
    https://your-app-name.herokuapp.com/ | https://git.heroku.com/your-app-name.git

Create a PostgreSQL database with Heroku. We will use the free "hobby-dev" model as an example.

    $ heroku addons:create heroku-postgresql:hobby-dev --app your-app-name
    Creating heroku-postgresql:hobby-dev on ⬢ your-app-name... free
    Database has been created and is available
    ! This database is empty. If upgrading, you can transfer
    ! data from another database with pg:copy
    Created postgresql-metric-19347 as DATABASE_URL
    Use heroku addons:docs heroku-postgresql to view documentation

Commit your work to your repository.

    $ git commit -am "Let's do this"

Push to Heroku.

    $ git push heroku master
    Counting objects: 19, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (16/16), done.
    Writing objects: 100% (19/19), 7.08 KiB | 0 bytes/s, done.
    Total 19 (delta 3), reused 14 (delta 1)
    remote: Compressing source files... done.
    remote: Building source:
    remote:
    remote: -----> Python app detected
    remote: -----> Installing python-3.6.8
    remote: -----> Installing pip
    remote: -----> Installing dependencies with Pipenv 2018.5.18…
    remote:        Installing dependencies from Pipfile.lock (e43d66)…
    remote: -----> Installing SQLite3
    remote: -----> $ python manage.py collectstatic --noinput
    remote:        120 static files copied to '/tmp/build_b643885c9c9ddd78d3e374fcf9348d40/staticfiles', 365 post-processed.
    remote:
    remote: -----> Discovering process types
    remote:        Procfile declares types -> release, web
    remote:
    remote: -----> Compressing...
    remote:        Done: 63.5M
    remote: -----> Launching...
    remote:  !     Release command declared: this new release will not be available until the command succeeds.
    remote:        Released v5
    remote:        https://your-app-name.herokuapp.com/ deployed to Heroku
    remote:
    remote: Verifying deploy... done.
    remote: Running release command...
    remote:
    remote: Operations to perform:
    remote:   Apply all migrations: admin, auth, contenttypes, sessions
    remote: Running migrations:
    remote:   Applying contenttypes.0001_initial... OK
    remote:   Applying auth.0001_initial... OK
    remote:   Applying admin.0001_initial... OK
    remote:   Applying admin.0002_logentry_remove_auto_add... OK
    remote:   Applying admin.0003_logentry_add_action_flag_choices... OK
    remote:   Applying contenttypes.0002_remove_content_type_name... OK
    remote:   Applying auth.0002_alter_permission_name_max_length... OK
    remote:   Applying auth.0003_alter_user_email_max_length... OK
    remote:   Applying auth.0004_alter_user_username_opts... OK
    remote:   Applying auth.0005_alter_user_last_login_null... OK
    remote:   Applying auth.0006_require_contenttypes_0002... OK
    remote:   Applying auth.0007_alter_validators_add_error_messages... OK
    remote:   Applying auth.0008_alter_user_username_max_length... OK
    remote:   Applying auth.0009_alter_user_last_name_max_length... OK
    remote:   Applying auth.0010_alter_group_name_max_length... OK
    remote:   Applying auth.0011_update_proxy_permissions... OK
    remote:   Applying sessions.0001_initial... OK
    remote: Waiting for release.... done.
    To https://git.heroku.com/your-app-name.git
    * [new branch]      master -> master

Give it a second. Visit the administration panel for your application at [your-app-name.herokuapp.com/admin/](https://your-app-name.herokuapp.com/admin/).

![The end](https://i.imgur.com/0kl5pOs.png)

Don't forget to create a super user so you can login.

    $ heroku run python manage.py createsuperuser

[Young hearts, run free](https://www.youtube.com/watch?v=i1TDZtoq5PU).
