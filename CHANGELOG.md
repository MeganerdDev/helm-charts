# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased
### Changed
<!--- Renovate --->

## 1.1.2 - 2021-12-30
### Fixed
- [105](https://github.com/nautobot/helm-charts/issues/105) - Tests fail with `runAsNonRoot: true`

## 1.1.1 - 2021-12-29
- Update pre-commit hook pre-commit/pre-commit-hooks to v4.1.0
- Update Nautobot version to 1.2.2
- Upgraded Mariadb subchart from 10.1.1 to 10.2.0
- Upgraded PostgreSQL subchart from 10.13.14 to 10.14.0
- Upgraded PostgreSQL-HA subchart from 8.1.2 to 8.1.3
- Upgraded Redis subchart from 15.6.7 to 15.6.10

## 1.1.0 - 2021-12-20
### Added
- Security scanning provided by Snyk and Kubescan to CI process
- Security remediations for most findings from security scanners, notably:

```yaml
securityContext:
  allowPrivilegeEscalation: false
  capabilities:
    drop:
      - "ALL"
```

was added to nearly all containers.
- PostgreSQL High Availability support
- Redis Sentinel Support
- MySQL Support
- Support for scheduled jobs with Nautobot 1.2

### Changed
- Updated to Nautobot 1.2.1
- Improved Redis TLS documentation
- Upgraded sub-chart dependencies

## 1.0.4 - 2021-12-10
### Changed
- Update ghcr.io/nautobot/nautobot Docker tag to v1.1.6

## 1.0.3 - 2021-11-24
### Changed
- Update ghcr.io/nautobot/nautobot Docker tag to v1.1.5
### Added
- [#16](https://github.com/nautobot/helm-charts/issues/16) - Added backup and restore procedures.
- [#46](https://github.com/nautobot/helm-charts/issues/46) - Added documentation to enable PostgreSQL and Redis TLS.
- [#56](https://github.com/nautobot/helm-charts/issues/56) - Added Artifact Hub images annotation for image scanning on Artifact Hub.
- [#58](https://github.com/nautobot/helm-charts/issues/58) - Added annotations to the ServiceAccount.

## 1.0.2 - 2021-11-03
### Fixed
- [#50](https://github.com/nautobot/helm-charts/issues/50) - Integrated Redis chart sets `NAUTOBOT_REDIS_SSL=false` ignoring the `nautobot.redis.ssl` value.

## 1.0.1 - 2021-10-28
### Fixed
- [#43](https://github.com/nautobot/helm-charts/issues/43) - Nautobot resources/limits reversed in default values.yaml.

## 1.0.0 - 2021-10-27
### Added
- Initial Release