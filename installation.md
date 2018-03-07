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
