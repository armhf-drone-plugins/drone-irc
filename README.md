# drone-irc

[![Build Status](https://armdrone.strahlungsfrei.de/api/badges/armhf-drone-plugins/drone-irc/status.svg)](https://armdrone.strahlungsfrei.de/armhf-drone-plugins/drone-irc)

armhf port of drone-plugins/drone-irc

Drone plugin to send build status notifications via IRC

## Binary

Build the binary using `make`:

```
make deps build
```

### Example

```sh
./drone-irc <<EOF
{
    "repo": {
        "clone_url": "git://github.com/drone/drone",
        "owner": "drone",
        "name": "drone",
        "full_name": "drone/drone"
    },
    "system": {
        "link_url": "https://beta.drone.io"
    },
    "build": {
        "number": 22,
        "status": "success",
        "started_at": 1421029603,
        "finished_at": 1421029813,
        "message": "Update the Readme",
        "author": "johnsmith",
        "author_email": "john.smith@gmail.com"
        "event": "push",
        "branch": "master",
        "commit": "436b7a6e2abaddfd35740527353e78a227ddcb2c",
        "ref": "refs/heads/master"
    },
    "workspace": {
        "root": "/drone/src",
        "path": "/drone/src/github.com/drone/drone"
    },
    "vargs": {
        "channel": "development",
        "nick": "test-drone",
        "server": {
            "port": 6697,
            "host": "irc.foobar.com",
            "password": "pa$$word",
            "tls": true
        }
    }
}
EOF
```

## Docker

Build the container using `make`:

```
make deps docker
```

### Example

```sh
docker run -i plugins/drone-irc <<EOF
{
    "repo": {
        "clone_url": "git://github.com/drone/drone",
        "owner": "drone",
        "name": "drone",
        "full_name": "drone/drone"
    },
    "system": {
        "link_url": "https://beta.drone.io"
    },
    "build": {
        "number": 22,
        "status": "success",
        "started_at": 1421029603,
        "finished_at": 1421029813,
        "message": "Update the Readme",
        "author": "johnsmith",
        "author_email": "john.smith@gmail.com"
        "event": "push",
        "branch": "master",
        "commit": "436b7a6e2abaddfd35740527353e78a227ddcb2c",
        "ref": "refs/heads/master"
    },
    "workspace": {
        "root": "/drone/src",
        "path": "/drone/src/github.com/drone/drone"
    },
    "vargs": {
        "channel": "development",
        "nick": "test-drone",
        "server": {
            "port": 6697,
            "host": "irc.foobar.com",
            "password": "pa$$word",
            "tls": true
        }
    }
}
EOF
```
