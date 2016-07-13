# Canal Curta Submission VM

## Clone

git clone --recursive git@github.com:mvsantoss/curta-submission-vm.git

## Run VM

vagrant up

## Configure App

Create file submission/.env with contents:

```
DEBUG=True
STATIC_URL=/static/
DATABASE_URL='mysql://root:@localhost/cc-submission'
DEFAULT_FROM_EMAIL=
EMAIL_HOST=
EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
EMAIL_PORT=
```

## Migrate

vagrant ssh

cd /vagrant/submission

source env/bin/activate && python manage.py migrate

## Create Admin User

vagrant ssh

cd /vagrant/submission

source env/bin/activate && python manage.py createsuperer

## Run Server

vagrant ssh

cd /vagrant/submission

source env/bin/activate && python manage.py runserver 192.168.55.10:8000