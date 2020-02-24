# Practical Microservices Workshop

More will come later, but for right now, this repo will verify that you can install and run what you need to for the workshop.

This workshop uses [Node.js](https://nodejs.org/en/) for the code and [Docker](https://www.docker.com/) for running databases.

## Installation Instructions

1. Install Node.js v12.13.1
    * If you're on MacOS or *nix, I recommend [`nvm`](https://github.com/nvm-sh/nvm)
    * If you're on Windows, I've heard good things about [`nvm-windows`](https://github.com/coreybutler/nvm-windows)
2. [Install Docker for your platform](https://docs.docker.com/v17.09/engine/installation/)

## Install Project Dependencies

From within the project folder, run `npm install`

## Verify Installation

1. Run databases 
  * `docker-compose rm -sf`
  * `docker-compose up`
2. Run verification script from this repo
  * `nvm use`
  * `npm install`
  * `node script/verify-installation.js`
  * Your results should look something like:

```
$ node script/verify-installation.js
Wrote message: bd78ff30-7802-45e2-bedd-5f34ce6e529d
Read back: {
  "id": "bd78ff30-7802-45e2-bedd-5f34ce6e529d",
  "stream_name": "verification-9d34a597-52d4-4b10-8b1e-955a6cfe283a",
  "type": "InstallationVerified",
  "position": "0",
  "global_position": "2",
  "data": "{\"verified\": \"2019-12-15T07:32:46.103Z\"}",
  "metadata": "{}",
  "time": "2019-12-15T14:32:46.135Z"
}
```

## Other Useful Software

* A database viewer, such as TablePlus (https://tableplus.com/).  It absolutely does not have to be this particular one, but you will benefit greatly from having something that will let you view the contents of the databases started in the `docker-compose.yml` file.

## Verify You Can Access The Databases

There are 2 databases in `docker-compose.yml`.  You can access them with the following connection params:

```
// Database 1 (SPOILER ALERT: we'll end up calling this the View Data database)
User: postgres
Host/Socket: 127.0.0.1
Port: 5432
Database: practical_microservices
Password: <It's blank.  As in literally blank.  Don't put all of this in there.>

// Database 2 (the Message Store database)
User: postgres
Host/Socket: 127.0.0.1
Port: 5433
Database: message_store
Password: <It's blank.  As in literally blank.  Don't put all of this in there.>
```

Obviously, if you don't use the provided Docker setup, then this connection info might not match what you have.  It's up to you, but for the purposes of the workshop, we'll assume you are using the provided Docker setup.


## Slides

[There are slides for this workshop](https://docs.google.com/presentation/d/1xhpC7SqrIUBo1ar4ykN7a0-snipIVtnpcpHYIauafGU/edit?usp=sharing).

## Instructor Guide

The script we'll follow is in the `instructor-guide.md` file in this repo.

