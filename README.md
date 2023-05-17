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

### Mattermost settings

The following variables are used to configure the Mattermost server.

```yaml
mattermost_url: https://mattermost.example.com
```

The mattermost url.

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

[0]: https://github.com/mattermost/mattermost-server
[1]: https://github.com/geerlingguy/ansible-role-postgresql/
