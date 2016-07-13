# Canal Curta Submission VM

## Clone

git clone --recursive git@github.com:mvsantoss/curta-submission-vm.git

## Run VM

vagrant up

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