# Shopee Coins Check-in

Check-in to Shopee and get coins automatically 😀😀

> **Warning**
> This bot is only tested for Taiwan users, who uses [Shopee Taiwan](https://shopee.tw/).

## Usage

```sh
docker run -it hyperbola/shopee-coins-bot:v1 --help
```

### Options

Each option is optional.

`-u`, `--user`: shopee username
`-p`, `--pass`: shopee password
`-P`, `--path-to-pass`: shopee password file
`-c`, `--cookie`: cookie file
`-x`, `--no-sms`: do not login with SMS; default to `false`
`-f`, `--force`: no error if coins already received; default to `false`

Shopee username is determined in the following order. The first meet is the final result.

1. environment var `USERNAME`
2. argument `--user`

Shopee password is determined in the following order. The first meet is the final result.

1. environment var `PASSWORD`
2. argument `--pass`
3. argument `--path-to-pass`

## Login

The bot tries to login user Shopee account in the following order. If the former one fails, the bot tries to use the next one until success.

1. saved cookies if given
2. username and password if both username and password are set

If `--cookie` is set, the bot tries to login using cookies. Cookies are updated if login succeeded.
