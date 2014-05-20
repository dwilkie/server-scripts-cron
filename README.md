# Nuntium Server Scripts

Server Scripts for Nunitum

## Installation

```
bundle exec foreman export upstart cron/ -t export/cron/ -e .env.production && mv cron/app-disk_usage-1.conf cron/disk_usage && chmod 700 cron/disk_usage && rm cron/app.conf && rm cron/app-disk_usage.conf
```
