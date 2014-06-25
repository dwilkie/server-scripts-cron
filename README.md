# server-scripts-cron

Uses a [Procfile](https://github.com/dwilkie/server-scripts-cron/blob/master/Procfile) to export [server-scripts](https://github.com/dwilkie/server-scripts) for cron or in other environments.

## Installation

```
git clone git://github.com/dwilkie/server-scripts-cron
cd server-scripts-cron
bundle install --path vendor
```

## Configuration

Fill out your [Procfile](https://github.com/dwilkie/server-scripts-cron/blob/master/Procfile) and `.env.production` file with your configuration.

## Generating Cron Scripts

The following command will generate cron scripts for the files in your [Procfile](https://github.com/dwilkie/server-scripts-cron/blob/master/Procfile) under the [cron directory](https://github.com/dwilkie/server-scripts-cron/tree/master/cron)

```
bundle exec foreman export upstart cron/ -t export/cron/ -e .env.production && mv cron/app-disk_usage-1.conf cron/disk_usage && chmod 700 cron/disk_usage && rm cron/*.conf
```

## Installing Cron Jobs

Run `crontab -e` and install the cron job with a line like:

```
0 22 * * * /bin/bash -l -c '/path/to/generated/file'
```
