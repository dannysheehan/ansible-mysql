# Ansible Role: mysql

Ansible playbook for installing MySQL Server on CentOS/Debian Linux

## Forked Changes by danny

- Added mysql certificate generation.
- Canges to detect password changes and also to detect initial random password for Centos7
- Downloads community addition of MYSQL for Centos7


## Usage

	git clone git@github.com:dannysheehan/ansible-role-mysql mysql


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

