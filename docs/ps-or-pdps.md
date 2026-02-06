# Choose Between Percona Server for MySQL and Percona Distribution for MySQL

When setting up Percona repositories, you can choose between two paths: Percona Distribution for MySQL or Percona Server for MySQL alone. Both use the same core database engine but are designed for different operational scopes.

To read about the standalone server product, see the [Percona Server for MySQL 8.4 :octicons-link-external-16:](https://docs.percona.com/percona-server/8.4/) documentation.

## Check Platform Support

Before choosing a repository, verify that your operating system version is supported for that specific product.

Review the [Percona Software and Platform Lifecycle :octicons-link-external-16:](https://www.percona.com/services/policies/percona-software-support-lifecycle#mysql) page to confirm support for your platform and version.

## Comparison Overview

| Feature | Percona Distribution for MySQL (`pdps-8.4`) | Percona Server for MySQL (`ps-84`) |
| --- | --- | --- |
| Primary Goal | A curated collection of components tested together as a complete enterprise stack. | A performance-enhanced, drop-in replacement for MySQL Community Edition. |
| Included Components | Database server, Percona XtraBackup, HAProxy, ProxySQL, and Orchestrator. | Database server, client, and essential plugins. |
| Release Cycle | Follows a coordinated release cycle where all bundled components are validated for inter-compatibility. | Follows the MySQL Community release cadence. |
| Ideal For | High Availability (HA) clusters and mission-critical enterprise environments. | Standalone instances or simple primary/replica setups. |

## Which one should I install?

### Percona Distribution for MySQL

Choose the Distribution (this product) if any of the following apply:

* Deploying a High Availability (HA) environment (e.g., using Percona XtraDB Cluster).

* Wanting Percona to guarantee that the specific versions of the server, proxy, and backup tools provided are fully compatible and tested as a single unit.

* Preferring a single repository entry-point that provides all the tools required for a full production lifecycle (Server + Backups + Management).

### Percona Server for MySQL

Choose standalone Percona Server for MySQL if any of the following apply:

* Wanting a minimal footprint focused solely on the database engine.

* Managing your own infrastructure components (backups, proxies, or orchestration) independently.

* Requiring the latest performance patches and features available in Percona Server but not needing a bundled ecosystem.

## Installation

For information on installing your choice, review the following:

* Percona Distribution for MySQL (this product): [Install Percona Distribution for MySQL 8.4](installing.md)

* Percona Server for MySQL (standalone): [Install Percona Server for MySQL 8.4 :octicons-link-external-16:](https://docs.percona.com/percona-server/{{vers}}/installation.html)
