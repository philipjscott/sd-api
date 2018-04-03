# sd-api

A simple bash script to make /GET requests against the SD API without having to worry about JWTs.

**Depends on [jq](https://stedolan.github.io/jq/)**

# Installation

```bash
$ sudo ./install.sh
```

This will put `sd-api` in `/usr/local/bin`.

In addition, you need the following code to your `~/.bashrc` or `~/zshrc` or `~/.profile`, etc.:

```bash
# This is just an example; you'll need to set them to point to YOUR Screwdriver instance

export SD_INSTANCE=https://api.screwdriver.cd/
export SD_NAMESPACE=v4
export SD_ACCESS_TOKEN=SECRET
. sd-api
```

`. sd-api` will set `$SD_JWT` so you won't need to fetch a JWT for each request.

### How to get a Screwdriver Access Token

1. Go to "User Settings"

![step1](https://raw.githubusercontent.com/ScottyFillups/sd-api/master/screenshots/step1.png)

2. Provide a name and description, then click "add"

![step2](https://raw.githubusercontent.com/ScottyFillups/sd-api/master/screenshots/step2.png)

# Usage

`sd-api` only supports `/GET`s right now; it takes the URI as an argument. _Do not begin the URI with a /_

```bash
$ sd-api stats
```
