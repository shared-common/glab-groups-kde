# glab-groups-kde

Thin GitHub Actions wrapper for the KDE Invent top-level group mirror.

## Scope

- Loads `gh-actions-cfg/glab-groups-kde`
- Calls the reusable workflow in `glab-groups-shared@mcr/main`
- Uses the BWS target PAT secret `GL_PAT_GROUP_KDE_SVC`
- Mirrors the checked-in KDE top-level group allowlist from
  `gh-actions-cfg/glab-groups-kde/groups.jsonl` into `kde/*` beneath
  `glab-forks`
- Runs deterministic mirror batch shards with five jobs max in parallel
- Schedules at minute 5 of hours 4, 10, 16, and 22 UTC
- Publishes discovery, plan, report, CSV, JSON, and Parquet artifacts for each run

## Validation

```sh
python3 -m unittest discover -s tests
```
