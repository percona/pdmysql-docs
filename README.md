# Percona Distribution for MySQL documentation.

Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

Welcome to Percona Distribution for MySQL documentation!

## Overview

Percona Distribution for MySQL is a combination of enterprise components from the MySQL open source community, designed and tested to work together. 

Percona Distribution for MySQL provides two deployment variants: one is Percona Server for MySQL-based and another one is Percona XtraDB Cluster-based. Each deployment is available via its own repository and includes the base server (Percona Server for MySQL or Percona XtraDB Cluster) and components. The table below lists what components are available with each server:

|Components	        |Percona Server for MySQL	|Percona XtraDB Cluster|
|-------------------|---------------------------|----------------------|
|Orchestrator	    |YES	                    |NO                    |
|HAProxy            |NO                         |YES                   |
|ProxySQL           |YES                        |YES                   |
|Percona XtraBackup |YES                        |YES                   |
|Percona Toolkit	|YES                        |YES                   |
|MySQL Shell        |YES                        |NO                    |
|MySQL Router       |YES                        |NO                    |

 
This repository contains the source files for [Percona Distribution for MySQL documentation](https://www.percona.com/doc/percona-distribution-mysql/8.0/index.html). The documentation is written in [reStructured text markup language](https://docutils.sourceforge.io/rst.html) and is created using [Sphinx Python Documentation Generator](https://www.sphinx-doc.org/en/master/). 

## Contributing

We welcome all contributions and are always looking for new members that are as dedicated to serving the community as we are. You can reach out to us using our [forums](https://forums.percona.com/c/mysql-mariadb/percona-distribution-for-mysql/42) and [Jira issue tracker](https://jira.percona.com/projects/DISTMYSQL/issues). 

For how to contribute to documentation, read the [Contributing guide](https://github.com/percona/pdmysql-docs/blob/8.0/CONTRIBUTING.md).

## License

Percona Distribution for MySQL documentation is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg