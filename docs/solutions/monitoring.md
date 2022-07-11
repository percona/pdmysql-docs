# Measurement and monitoring

To ensure that database infrastructure is performing as intended or at its best, specific metrics need to be measured and alerts are to be raised when some of these metrics are not in line with expectations. A periodic review of these measurements is also encouraged to promote stability and understand potential risks associated with the database infrastructure.

The following are the 3 aspects of database performance measurement and monitoring:


* **Measurement** - To understand how a database infrastructure is performing,  multiple aspects of the infrastructure need to be measured. With measurement it’s important to understand the impact of the sample sizes, sample timing, and sample types.


* **Metrics** - Metrics refer to the actual parts of the database infrastructure being measured. When we discuss metrics, more isn’t always better as it could introduce unintentional noise or make troubleshooting overly burdensome.


* **Alerting** - When one or many metrics of the database infrastructure is not within a normal or acceptable range, an alert should be generated so that the team responsible for the appropriate portion of the database infrastructure can investigate and remedy it.

Monitoring and measurement for this solution are covered by [Percona Monitoring and Management](https://www.percona.com/software/database-tools/percona-monitoring-and-management). It has a specific dashboard to monitor the Group Replication state and cluster status as a whole. For more information, read [Percona Monitoring and Management Documentation](hhttps://docs.percona.com/percona-monitoring-and-management/index.html).