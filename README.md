# Mattermost

> Ansible role to install a mattermost server.

## Variables

```yaml
mattermost_version: 7.8.5
```

The [`mattermost`][0] version to download.

```yaml
mattermost_postgres_user: mattermost
mattermost_postgres_password: secret
mattermost_postgres_db: mattermost
```

Database credentials. The database and user will be created with [`geerlingguy.postgresql`][1].

```yaml
mattermost_destination: /opt
```

The destination where the server will be installed.

```yaml
mattermost_data_dir: /data/mattermost/data
```

Data directory where mattermost stores plugins, files, custom emojis, etc..

```yaml
mattermost_service_name: mattermost
```

The name of the systemd unit file.

### Mattermost settings

The config file template packaged with the role is very generic and only some
basic settings can be configured with the role variables.

If that's not enough you can replace the default template with your own:

* create a `templates` directory at the same level as your playbook
* create a `templates/myconfig.json.j2` file (don't use the name of the default template, `default_config_template.json.j2`)
* set the `mattermost_config_file_template` to `myconfig.json.j2` or the name of your file

If you use the default template you can use the following variables to change
some basic settings.

```yaml
mattermost_url: https://mattermost.example.com
```

The mattermost url.

```yaml
mattermost_listen_address: ":8065"
```

The address and port to which to bind and listen (the default binds to all network interfaces).

```yaml
mattermost_site_name: ""
```

The site name.

```yaml
mattermost_brand_text: ""
```

The brand text.

```yaml
mattermost_email: no-reply@example.com
```

From address used when sending email from mattermost.

```yaml
mattermost_smtp_user: no-reply@example.com
mattermost_smtp_password: secret
mattermost_smtp_server: smtp.example.com
mattermost_smtp_port: 587
mattermost_smtp_security: STARTTLS
```

SMTP settings and credentials.

```yaml
mattermost_creation_domains: []
```

A list of mail domains that will be allowed to create users.

## Dependencies

* [`geerlingguy.postgresql`][1]

[0]: https://github.com/mattermost/mattermost-server
[1]: https://github.com/geerlingguy/ansible-role-postgresql/
