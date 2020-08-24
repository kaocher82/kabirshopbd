# Shuup Project Template

Use this template for simple Django project with Shuup.

1. Clone to your local environment
2. Install and test Shuup without workbench
3. Attach your addons and custom business logic
4. Push to your project repository

## Installation

1. Create and activate fresh Python virtualenv
2. Run `pip install -r requirements.txt`.
3. Optionally copy .env.template to .env and setup environment variables for your project.
   You can also modify Django settings directly to the settings file or setup local settings file.
4. Initialize database by running `python manage.py migrate`
5. Initialize installation by running `python manage.py shuup_init`
6. Create superuser to access admin `python manage.py createsuperuser`
7. Run server `python manage.py runserver 0.0.0.0:8888`
8. Navigate to `127.0.0.1:8888/sa` and login
9. Complete Shuup onborading wizard and you should be all set
10. Now for your own project you can just update ``git remote`` with your
    own git repository and start pushing new commits. For example
    ``git remote set-url origin git@github.com:username/shuup-project-template.git``
    # Django sample for Google App Engine Flexible Environment

    [![Open in Cloud Shell][shell_img]][shell_link]

    [shell_img]: http://gstatic.com/cloudssh/images/open-btn.png
    [shell_link]: https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/GoogleCloudPlatform/python-docs-samples&page=editor&open_in_editor=appengine/flexible/hello_world_django/README.md

    This is a basic hello world [Django](https://www.djangoproject.com/) example
    for [Google App Engine Flexible Environment](https://cloud.google.com/appengine).

    ## Running locally

    You can run locally using django's `manage.py`:

        $ python manage.py runserver

    ## Deployment & how the application runs on Google App Engine.

    Follow the standard deployment instructions in
    [the top-level README](../README.md). Google App Engine runs the application
    using [gunicorn](http://gunicorn.org/) as defined by `entrypoint` in
    [`app.yaml`](app.yaml). You can use a different WSGI container if you want, as
    long as it listens for web traffic on port `$PORT` and is declared in
    [`requirements.txt`](requirements.txt).

    ## How this was created

    This project was created using standard Django commands:

        $ virtualenv env
        $ source env/bin/activate
        $ pip install django gunicorn
        $ pip freeze > requirements.txt
        $ django-admin startproject kabirshopbd
        $ python manage.py startapp project

    Then, we added a simple view in `hellworld.views`, added the app to
    `project_name.settings.INSTALLED_APPS`, and finally added a URL rule to
    `project_name.urls`.

    In order to deploy to Google App Engine, we created a simple
    [`app.yaml`](app.yaml).

    ## Database notice

    This sample project uses Django's default sqlite database. This isn't suitable
    for production as your application can run multiple instances and each will
    have a different sqlite database. Additionally, instance disks are ephemeral,
    so data will not survive restarts.

    For production applications running on Google Cloud Platform, you have
    the following options:

    * Use [Cloud SQL](https://cloud.google.com/sql), a fully-managed MySQL database.
      There is a [Flask CloudSQL](../cloudsql) sample that should be straightfoward
      to adapt to Django.
    * Use any database of your choice hosted on
      [Google Compute Engine](https://cloud.google.com/compute). The
      [Cloud Launcher](https://cloud.google.com/launcher/) can be used to easily
      deploy common databases.
    * Use third-party database services, or services hosted by other providers,
      provided you have configured access.

