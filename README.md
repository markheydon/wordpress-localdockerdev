# WordPress Local Docker development setup

Often have a need to make a quick 'dev' copy of a live site locally for debugging, testing, quick tweaks, etc.etc. Also got sick of fighting with wordmove everytime I sit down on a new device!

Known to work on both Ubtunu and Windows via WSL2 (running Ubuntu) but in no way has this been extensively tested - I use this files regularly without issue but can't guarentee will work for everyone.

## Overview

Repo not really designed to be used on a project but rather a collection of files that can be quickly deployed to get a fairly usable docker-compose setting up and running to do some quick level WordPress development.

General idea is copy the files to a project folder somewhere, create a ```.env``` file with relevant details, copy the movefile.yml file into the ```./html``` folder and amend as needed (probably only the product URL needs setting -- should probably move that to the .env file really?) then run ```wordmove``` to pull a copy from the server to local setup.

**NOTE**: SSH setup is expected to be working on the local system.

**NOTE**: It is expected you know what docker compose is and how to use it.

### Sample .env file
```
### SECURITY WARNING: DO NOT CHECK THIS FILE INTO SOURCE CONTROL

# WordPress database table prefix - used for both local/dev and production especially when using wordmove.
PROD_DB_PREFIX="klas_"

# Database access details at the production server end, used by wordmove.
PROD_DB_NAME="database_name"
PROD_DB_USER="database_username"
PROD_DB_PASS="database_password"

# Wordmove specific setting: location of the files on the production box.
PROD_SITE_PATH="/sites/example.com/html"

# Wordmove specific settings for accessing the production box.
PROD_SSH_HOST="servername.example.com"
PROD_SSH_USER="ssh_username"
```
