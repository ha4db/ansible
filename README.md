# Ha4db ansible

Install dependency and setup everything for `ha4db`.

## How to use

1. Setup instance via [ha4db-ec2](https://github.com/ha4db/aws-ec2) or setup ubuntu 20.04 instance.
2. [Setup ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu) if you need.
3. Run ansible-playbook

```sh
ansible-playbook ha4db.yml
```

## Create Administrator user

You need to create administrator user at first.

First, run `rails console` with production environment.

```sh
sudo su - appsrv
cd /srv/ha4db/app/current
bin/rails console -e production
```

In Rails console:

```ruby
a = AdminUser.new
a.login_name = "your_name"
a.password = "your_password"
a.save
```
