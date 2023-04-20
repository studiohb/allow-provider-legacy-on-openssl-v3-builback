# allow-provider-legacy-on-openssl-v3-builback heroku-22 Buildpack

This is a [Heroku buildpack][0] for add legacy provider option to openssl V3 in order to execute old cipher.

## Versions

* Buildpack:   `0.1`

## Usage

[Add this buildpack][2] to your Heroku application to add this config to your /etc/ssl/openssl.cnf file:

```
[provider_sect]
default = default_sect
legacy = legacy_sect

[default_sect]
activate = 1

[legacy_sect]
activate = 1
```


```bash
$ heroku buildpacks:add https://github.com/ --index 1
```

### Clearing Repo Cache

Remember to clean your repository cache if you are updating the version of
buildpack. To do that, run:

```bash
$ heroku plugins:install https://github.com/heroku/heroku-repo.git
$ heroku repo:purge_cache -a appname
```
