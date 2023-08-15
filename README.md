[![Health Check](../../actions/workflows/health-check.yml/badge.svg)](../../actions/workflows/health-check.yml)

# Quilt's Status Page

Forked from [statsig's template](https://github.com/statsig-io/statuspage/) and [statsig's page](https://github.com/statsig-io/statsigstatus/)

## Page

- https://status.quilt.app

## Setup instructions

1. Add new urls to `urls.cfg` to include new urls.

```cfg
key1=https://example.com
key2=https://statsig.com
```

## How does it work?

This project uses GitHub actions to wake up every hour and run a shell script (`health-check.sh`). This script runs `curl` on every url in your config and appends the result of that run to a log file and commits it to the repository. This log is then pulled dynamically from `index.html` and displayed in a easily consumable fashion. You can also run that script from your own infrastructure to update the status page more often.
