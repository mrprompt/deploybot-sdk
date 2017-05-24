# Deploybot SDK

[![Build Status](https://travis-ci.org/mrprompt/deploybot-sdk.svg?branch=master)](https://travis-ci.org/mrprompt/deploybot-sdk)
[![Code Climate](https://codeclimate.com/github/mrprompt/deploybot-sdk/badges/gpa.svg)](https://codeclimate.com/github/mrprompt/deploybot-sdk)
[![Test Coverage](https://codeclimate.com/github/mrprompt/deploybot-sdk/badges/coverage.svg)](https://codeclimate.com/github/mrprompt/deploybot-sdk/coverage)
[![Issue Count](https://codeclimate.com/github/mrprompt/deploybot-sdk/badges/issue_count.svg)](https://codeclimate.com/github/mrprompt/deploybot-sdk)
[![GitHub issues](https://img.shields.io/github/issues/mrprompt/deploybot-sdk.svg)](https://github.com/mrprompt/deploybot-sdk/issues)
[![GitHub stars](https://img.shields.io/github/stars/mrprompt/deploybot-sdk.svg)](https://github.com/mrprompt/deploybot-sdk/stargazers)
[![GitHub license](https://img.shields.io/badge/license-AGPL-blue.svg)](https://raw.githubusercontent.com/mrprompt/deploybot-sdk/master/LICENSE)

A library to [Deploybot](https://www.deploybot.com) API.

## Install

```
pip install deploybot-sdk
```

## Usage

```
from deploybot.client import Client
from deploybot.user import User
import os

account = os.environ.get('DEPLOYBOT_ACCOUNT')
token = os.environ.get('DEPLOYBOT_TOKEN')

client = Client(account, token)
repository = Repository(client)

print(repository.list())
print(repository.get(99999))

```

## Test

```
python setup.py test
```