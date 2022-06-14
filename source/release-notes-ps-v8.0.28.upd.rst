.. _pdps.8.0.28.upd:

********************************************************************************
|pdmysql| 8.0.28 using Percona Server for MySQL Update (|date|)
********************************************************************************

:Date: |date|
:Installation: :ref:`installation`

|pdmysql| is a single solution with the best and most critical enterprise components from the |mysql| open-source community, designed and tested to work together. 

This update of |pdmysql| using |PS| is based on `Percona Server for MySQL 8.0.28-20 <https://www.percona.com/doc/percona-server/8.0/release-notes/Percona-Server-8.0.28-20.html>`_. It also includes the updated version of `Percona XtranBackup 8.0.28-21 <https://docs.percona.com/percona-xtrabackup/latest/release-notes/8.0/8.0.28-21.0.html>`_.

Release Highlights
=================================================

* `Encryption functions and variables <https://www.percona.com/doc/percona-server/8.0/security/encryption-functions.html>`__ to manage the encryption range are added. The functions may take an algorithm argument. Encryption converts plaintext into ciphertext using a key and an encryption algorithm.

  You can also use the user-defined functions with the PEM format keys generated externally by the OpenSSL utility.

* Support for the `Amazon Key Management Service (AWS KMS) component <https://www.percona.com/doc/percona-server/8.0/security/using-amz-kms.html>`__.

* Error messages are now logged to a memory buffer.

* ZenFS file system plugin for RocksDB is updated to version 2.1.0.

* Memory leak and errors detectors (Valgrind or AddressSanitizer) provide detailed stack traces from dynamic libraries (plugins and components). The detailed stack traces make it easier to identify and fix the issues.

Other components, supplied with |pdmysql|, remain unchanged.

.. |date| replace:: June 20, 2020
.. include:: .res/replace.txt
