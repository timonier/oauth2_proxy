# README

A reverse proxy that provides authentication with Google, Github or other provider

⚠️ This project is no longer maintained. ⚠️

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://github.com/timonier/oauth2_proxy/raw/master/bin/installer" | sudo sh -s -- install
```

__Note__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

## Usage

Run the command `oauth2_proxy`:

```sh
# See all oauth2_proxy options

oauth2_proxy --help

# Run oauth2_proxy

export CLIENT_ID="...."
export CLIENT_SECRET="...."
export COOKIE_SECRET="$(bin/generate-secret)"

oauth2_proxy --authenticated-emails-file=/tmp/oauth2_emails --client-id="${CLIENT_ID}" --client-secret="${CLIENT_SECRET}" --cookie-secret="${COOKIE_SECRET}" --cookie-secure=false  --http-address=:80  --provider=github  --upstream="http://127.0.0.1:9000/"
```

## Links

* [bitly/oauth2_proxy](https://github.com/bitly/oauth2_proxy)
* [image "timonier/oauth2_proxy"](https://hub.docker.com/r/timonier/oauth2_proxy/)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
