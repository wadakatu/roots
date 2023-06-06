# Docker Environment for Roots Stack

### Roots is Advanced WordPress Development Tools.

https://roots.io/

#### This repository provides docker environment for building Roots stack quickly.

## Prerequisite

- docker & docker compose installed on local machine
- Node v18.16.0 installed on local machine
- Yarn v1 installed on local machine

## How to use

### 1. clone this repository

```
git clone https://github.com/wadakatu/roots.git
```

### 2. copy .env file

```
cp .env.example .env
```

### 3. edit .env file

```
DB_NAME=sample-db
DB_USER=wordpress
DB_PASSWORD=sample
``` 

### 4. start up docker

```
docker compose up -d
```

### 5. get into php container

```
docker compose exec php bash
```

### 6. install Bedrock in php container

```
composer create-project roots/bedrock
```

### 7. edit .env file in bedrock directory

```
vim bedrock/.env
```

#### ENV

```
WP_ENV='development'
```

#### DB

Enter the same value as entered the .env file in the base directory.

```
DB_HOST=db
DB_NAME='sample-db'
DB_USER='wordpress'
DB_PASSWORD='sample'
```

#### KEYS

Generate your keys here: https://roots.io/salts.html

```
AUTH_KEY='sample-key'
SECURE_AUTH_KEY='sample-key'
LOGGED_IN_KEY='sample-key'
NONCE_KEY='sample-key'
AUTH_SALT='sample-key'
SECURE_AUTH_SALT='sample-key'
LOGGED_IN_SALT='sample-key'
NONCE_SALT='sample-key'
```

### 8. access localhost

```
http://localhost
```