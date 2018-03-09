## Install RabbitMQ testing package
* [debian-install](https://www.rabbitmq.com/install-debian.html)
* [rabbitmq-server-github](https://github.com/rabbitmq/rabbitmq-server/issues/515)
```sh
Install Erlang
cd /tmp/
wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb
sudo dpkg -i erlang-solutions_1.0_all.deb
sudo apt-get update -y
sudo apt-get install erlang -y

Install RabbitMQ from source
cd /tmp/
echo 'echo "deb http://www.rabbitmq.com/debian/ testing main" >> /etc/apt/sources.list' | sudo -s
wget https://www.rabbitmq.com/rabbitmq-signing-key-public.asc
sudo apt-key add rabbitmq-signing-key-public.asc
sudo apt-get update -y
sudo apt-get install rabbitmq-server -y
```

## Enable management plugin

```sh
rabbitmq-plugins enable rabbitmq_management
```
* The Web UI is located at: http://server-name:15672/

## Create User & Give Permission

* Add a new/fresh user, say user ` admin ` and password ` admin `
```sh
rabbitmqctl add_user admin admin
```
* Give administrative access to the ` admin ` user
```sh
rabbitmqctl set_user_tags admin administrator
```
* Set permission to newly created user
```sh
rabbitmqctl set_permissions -p / admin ".*" ".*" ".*"
```
