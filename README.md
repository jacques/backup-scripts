# Backup Scripts

Various backup scripts for backing up your Shared Hosting account on TextDrive's
Shared Hosting service.  Can also be used for backing up data on Joyent
SmartMachines.

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

```
#
# Backup Host
#
BACKUP_HOST=sftp.example.com
BACKUP_USER=username
BACKUP_SSH_IDENTITY=example
BACKUP_REMOTE_DIR=/path/to/backups/

RSYNC_OPTS=--delete-after
```

<table>
  <tr>
    <th>Key</th>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>BACKUP_HOST</td>
    <td>string</td>
    <td>Hostname or IP Address of the server where files are backed up to</td>
    <td>sftp.siberia.co.za</td>
  </tr>
  <tr>
    <td>BACKUP_USER</td>
    <td>string</td>
    <td>Username on the server specified in BACKUP_HOST</td>
    <td>jacques</td>
  </tr>
  <tr>
    <td>BACKUP_SSH_IDENTITY</td>
    <td>string</td>
    <td>The suffix on the ~/.ssh/id_rsa-IDENTITY used to authenticate to the BACKUP_HOST</td>
    <td>sftp</td>
  </tr>
  <tr>
    <td>BACKUP_REMOTE_DIR</td>
    <td>string</td>
    <td>The remote diretory where files are uploaded to</td>
    <td>/users/home/jacques/remote-backups/joey/</td>
  </tr>
</table>

### Generate a SSH public/private key-pair

Generate a public/private key-pair without a passphrase so that backups can be
uploaded offsite without prompting to enter a password or a pass phrase to unlock
the ssh private key.

```
ssh-keygen -t rsa -b 4096 -N ''
```

You may want to store this to generated key-pair to ~/.ssh/id_rsa-strongspace for a
public/private key-pair you just use with StrongSpace.

### Configuration files

Copy config.example to config so that the configuration can be sourced by the
various scripts.

## Contributing

1. Fork it.
2. Create a branch (git checkout -b fix-for-something)
3. Commit your changes (git commit -am "[#TICKET] Fixed something")
4. Push to the branch (git push origin fix-for-something)
5. Open a Pull Request
6. Enjoy a refreshing Dr Pepper and wait for the pull request to be merged

## License

```
Copyright (c) 2013 Jacques Marneweck. All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
