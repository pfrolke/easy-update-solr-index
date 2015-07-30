easy-update-solr-index
======================

Update the EASY SOLR Search Index with metadata from Fedora.

SYNOPSIS
--------

    easy-update-solr-index [-u <user> -p <password>][-f <fcrepo-server>][-s <solr-server-request-handler>] \
       [-x <output-xml-dir>] <easy-dataset-pid>...


DESCRIPTION
-----------

The EASY SOLR Search Index is a configured [Apache SOLR Service] that contains an index of the metadata stored
in the Fedora Commons Repository at the dataset level. This command extracts the required metadata from the 
Fedora Commons Repository and sends it to the EASY SOLR Search Index to add or update the record for the specified
dataset(s)

ARGUMENTS
---------

* ``-u``, ``--user`` -- Fedora user to connect with
* ``-p``, ``--password`` -- password of the Fedora user
* ``-f``, ``--fcrepo-server`` -- URL of the Fedora Commons Repository server
* ``-s``, ``--solr-server-request-handler`` -- URL of the EASY SOLR Search Index server request handler
* ``-x``, ``--output-xml-dir`` -- directory to write the documents to be sent to SOLR to
* ``<easy-datataset-pid>...`` -- one or more dataset PIDs 


INSTALLATION AND CONFIGURATION
------------------------------

### Installation steps:

1. Unzip the tarball to a directory of your choice, e.g. /opt/
2. A new directory called easy-update-solr-index-<version> will be created
3. Create an environment variabele ``EASY_UPDATE_SOLR_INDEX_HOME`` with the directory from step 2 as its value
4. Add ``$EASY_UPDATE_SOLR_INDEX_HOME/bin`` to your ``PATH`` environment variable.


### Configuration

General configuration settings can be set in ``$EASY_UPDATE_SOLR_INDEX_HOME/cfg/application.properties`` and 
logging can be configured in ``$EASY_UPDATE_SOLR_INDEX_HOME/cfg/logback.xml``. The available settings are explained in
comments in aforementioned files.


BUILDING FROM SOURCE
--------------------

Prerequisites:

* Java 7 or higher
* Maven 3.3.3 or higher
 
Steps:

1. Clone and build the [dans-parent] project (*can be skipped if you have access to the DANS maven repository*)
      
        git clone https://github.com/DANS-KNAW/dans-parent.git
        cd dans-parent
        mvn install
2. Clone and build this project

        git clone https://github.com/DANS-KNAW/easy-update-solr-index.git
        cd easy-update-solr-index
        mvn install


[Apache SOLR Service]: https://lucene.apache.org/solr/
