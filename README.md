# Backup Scripts

Various backup scripts for backing up your Shared Hosting account on TextDrive's
Shared Hosting service.

## Getting Started

Currenty expects to be run under SmartOS zones (useful if you're on a TextDrive
Shared Hosting account on SmartOS or a Joyent SmartMachine).

### MySQL

Expects a ~/.my.cnf file to be configured:

```
[client]
user = username
password = password
```

### PostgreSQL

Expects a ~/.pgpass file to be configured.

### Offsite Backups

Presently supports backing up to a remote SFTP location.

### Configuration files

Copy config.example to config so that the configuration can be sourced by the
various scripts.