# Deploybot SDK

[![Build Status](https://travis-ci.org/mrprompt/deploybot-sdk.svg?branch=master)](https://travis-ci.org/mrprompt/deploybot-sdk)
[![Code Climate](https://codeclimate.com/github/mrprompt/deploybot-sdk/badges/gpa.svg)](https://codeclimate.com/github/mrprompt/deploybot-sdk)
[![Test Coverage](https://codeclimate.com/github/mrprompt/deploybot-sdk/badges/coverage.svg)](https://codeclimate.com/github/mrprompt/deploybot-sdk/coverage)
[![Issue Count](https://codeclimate.com/github/mrprompt/deploybot-sdk/badges/issue_count.svg)](https://codeclimate.com/github/mrprompt/deploybot-sdk)
[![GitHub issues](https://img.shields.io/github/issues/mrprompt/deploybot-sdk.svg)](https://github.com/mrprompt/deploybot-sdk/issues)
[![GitHub stars](https://img.shields.io/github/stars/mrprompt/deploybot-sdk.svg)](https://github.com/mrprompt/deploybot-sdk/stargazers)
[![GitHub license](https://img.shields.io/badge/license-AGPL-blue.svg)](https://raw.githubusercontent.com/mrprompt/deploybot-sdk/master/LICENSE)

A library to [Deploybot](https://www.deploybot.com) API.

To see how to use, look [Cli](https://github.com/mrprompt/deploybot-cli).


## Install

```
pip install deploybot-sdk
```

## Usage

### Client

Client is the main library, this is responsible to make and receive requests from API.

The first step, is instantiate to your application using your account name and API token.

```python
from deploybot.client import Client
import os

account = os.environ.get('DEPLOYBOT_ACCOUNT')
token = os.environ.get('DEPLOYBOT_TOKEN')

client = Client(account, token)
```

### Repository

Get one or list repositories.


```python
from deploybot.repository import Repository

# client is defined before
client = object

repository = Repository(client)

# list all repositories
print(repository.list())

# get specific repository to details
print(repository.get(99999))

```

### Environment

Get one or list your environments


```python
from deploybot.environment import Environment

# client is defined before
client = object

environment = Environment(client)

# list all environments
repository = 1

print(environment.list(repository))

# get specific environment to details
environment = 1

print(environment.get(environment))

```

### Server

Get one or list your servers


```python
from deploybot.server import Server

# client is defined before
client = object

server = Server(client)

# list all servers
print(server.list())

# get specific server to details
print(server.get(123456))

```

### User

Get one or list users from account


```python
from deploybot.user import User

# client is defined before
client = object

user = User(client)

# list all users
print(user.list())

# get specific user to details
print(user.get(123456))

```

### Deploy

List, view and trigger a deploy.


```python
from deploybot.deploy import Deploy

# client is defined before
client = object

deploy = Deploy(client)

# list all deploys
repository = 1
environment = 2

print(deploy.list(repository, environment))

# get specific deploy to details
deploy_id = 123456

print(deploy.get(deploy_id))

# trigger a deploy
environment = 2

print(deploy.trigger(environment))

```


## Testing

```
python setup.py test
```
