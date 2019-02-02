# GoTo Bash Script

Script to SSH to hosts easily.

The purpose of this script is to ssh to a host using a small alias instead of remembering the full hostname.
This is archived by using a small plain text file as database. The structure of this file is described bellow to make it
easy to import/export.

### Parameters

You can either run `goto` and use the GUI or `goto <hostname or alias> to ssh a specific host.
Also using `goto -e` will open the script with nano to make any changes

### Operating Systems

This script uses dialog to create menus so will check and install needed packages only for ArchLinux/Mangaro or Ubuntu/Debian.

### Database

The database file is a simple text file, using tab separated values. Feel free to create your own or via GUI or with the following schema

|HOST NAME|ALIAS|HOSTNAME or IP|SSH PORT|USER|
|:-------:|:---:|:------------:|:------:|:--:|
|my_server|my|192.168.1.1|22|u|

Rules:
1. No spaces in any field
2. Host Name and Alias can be the same but not blank
3. User can be either r (root) or u (user). For user it's the user you are currently have on your system

### Configuration

Before start using this script, you need to configure the following values (in the top of the script)

- USER: the username of the user will use it, e.q. `myuser`
- SSH_KEY: the path of the key you use to connect, e.q. `~/.ssh/id_rsa`
- DB_FILE: the location to store the database file e.q. `~/scripts/goto.db`
- SCRIPT_FILE: the location of this script (so we can edit) `~/scripts/goto`
- OS: the operating system, for now will only accept `debian`, `ubuntu`, `archlinux` and `manjaro`

---

### Changelog

Version 2.10
- Think it's stable enough
- Script Location as parameter for edit to work (-e)

Version 2.05 Beta
- Rewrite all script and testing

---

### Known Problems

- On GUI server selection, ssh doesn't search aliases.
