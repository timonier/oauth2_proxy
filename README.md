# README

A reverse proxy that provides authentication with Google, Github or other provider

## Installation

Copy `bin/oauth2_proxy` into your executable folder (like `/usr/local/bin` or `$HOME/bin`):

```sh
sudo curl --location --output /usr/local/bin/oauth2_proxy "https://github.com/timonier/oauth2_proxy/raw/master/bin/oauth2_proxy"
sudo chmod +x /usr/local/bin/oauth2_proxy
```

Linux users can use the [installer](https://github.com/timonier/oauth2_proxy/blob/master/bin/installer):

```sh
curl --location "https://github.com/timonier/oauth2_proxy/raw/master/bin/installer" | sudo sh -s -- install
```

## Usage

Run the command `oauth2_proxy`:

```sh
# See all oauth2_proxy options

oauth2_proxy --help

# Run oauth2_proxy

export CLIENT_ID="...."
export CLIENT_SECRET="...."
export COOKIE_SECRET=$(bin/generate-secret)

oauth2_proxy \
    "--client-id=${CLIENT_ID}" \
    "--client-secret=${CLIENT_SECRET}" \
    "--cookie-secret=${COOKIE_SECRET}" \
    --authenticated-emails-file=/tmp/oauth2_emails \
    --http-address=:80
    --provider=github
    "--upstream=http://127.0.0.1:9000/" \
    --cookie-secure=false
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [bitly/oauth2_proxy](https://github.com/bitly/oauth2_proxy)
* [image "timonier/oauth2_proxy"](https://hub.docker.com/r/timonier/oauth2_proxy/)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
