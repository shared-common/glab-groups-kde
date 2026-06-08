# glab-groups-kde

Thin GitHub Actions wrapper for the KDE Invent top-level group mirror.

## Scope

- Loads `gh-actions-cfg/glab-groups-kde`
- Calls the reusable workflow in `glab-groups-shared@mcr/main`
- Uses the BWS target PAT secret `GL_PAT_GROUP_KDE_SVC`
- Mirrors the current public top-level `invent.kde.org` groups into `kde/*`
  beneath `GL_GROUP_TOP_GLAB_OWNER`
- Runs deterministic mirror batch shards with five jobs max in parallel
- Schedules at minute 5 of hours 4, 10, 16, and 22 UTC
- Publishes plan, report, CSV, JSON, and Parquet artifacts for each run

## Validation

```sh
python3 -m unittest discover -s tests
```
