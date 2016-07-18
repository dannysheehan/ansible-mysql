# Ansible Role: jeffhung.mysql

Ansible playbook for installing MySQL Server on CentOS/Debian Linux


## Usage

Install this playbook:

	ansible-galaxy install jeffhung.mysql


## Role Variables

### `mysql_root_password`

Configure the password for mysql root account.

### `mysql_databases`

List the databases to create. For example, the following configuration creates
two databases: `foo_db` and `bar_db`.

```yaml
mysql_databases:
  - name: foo_db
  - name: bar_db
```

### `mysql_users`

List other non-root mysql accounts to create. For example, the following
configuration creates two accounts: `foo_user` and `bar_user`, which could
access `foo_db` and `bar_db` respectively.

```yaml
mysql_users:
  - name: foo_user
    pass: y2TtnA5n
    priv: "foo_db.*:ALL"
  - name: bar_user
    pass: fGyvNb2s
    priv: "bar_db.*:ALL"
```


## License

BSD

