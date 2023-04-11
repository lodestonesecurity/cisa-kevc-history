# cisa_kevc_history

[![Latest Cisa KEV Data](https://github.com/lodestonesecurity/cisa_kevc_history/actions/workflows/scrape.yml/badge.svg?branch=main)](https://github.com/lodestonesecurity/cisa_kevc_history/actions/workflows/scrape.yml)

Every day tracking exploits from https://www.cisa.gov/known-exploited-vulnerabilities-catalog

Source JSON: https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json

## Analysing the results

Use [git-history](https://github.com/simonw/git-history) to load the history into SQLite:

```sh
git-history file vulns.db known_exploited_vulnerabilities.json \
            --id cveID \
            --ignore-duplicate-ids \
            --full-versions \
            --convert 'json.loads(content)["vulnerabilities"]'
```

You can use tools like [datasette](https://datasette.io/) to browse the data.
