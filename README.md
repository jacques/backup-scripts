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

### Configuration files

Copy config.example to config so that the configuration can be sourced by the
various scripts.

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
