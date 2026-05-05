# Test datasets for Apache Hive
A repository holding datasets and dumps that are used for testing Apache Hive.

## Metastore database dumps

A collection of database dumps obtained from various versions of Hive.
The dumps can be found in the GitHub release asserts. They are not under version control since they are in general large and not expected to change very often.
In addition, the dumps are in binary format so they cannot be easily inspected by humans.

#### Postgres

The database dumps were obtained from a Hive metastore running Cloudera's Hive 3.1.3000 using the following command:

    pg_dump -h localhost -p 5432 -U hive -d metastore -Fc > meta.dump.gz

Some manual post-processing has been performed to remove redundant information from the dump using the [cleanup.sql](metastore/cleanup.sql) file.
Nevertheless, the dumps may still contain additional databases and tables but these are not actively used.

##### TPC-DS

Metastore dumps from various [TPC-DS](http://www.tpc.org/tpcds/) scale factors.
* [metastore_tpcds10tb_3_1_3000](https://github.com/zabetak/hive-test-datasets/releases/download/1.0/metastore_tpcds10tb_3_1_3000.dump.gz)
* [metastore_tpcds30tb_3_1_3000](https://github.com/zabetak/hive-test-datasets/releases/download/1.0/metastore_tpcds30tb_3_1_3000.dump.gz)
