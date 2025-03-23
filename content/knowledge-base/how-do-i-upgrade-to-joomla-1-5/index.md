---
author: "icarnaghan"
title: "How do I upgrade to Joomla! 1.5 ?"
date: 2018-04-06
---

Joomla! 1.5 does not provide an upgrade path from earlier versions. Converting an older site to a Joomla! 1.5 site requires creation of a new empty site using Joomla! 1.5 and then populating the new site with the content from the old site. This migration of content is not a one-to-one process and involves conversions and modifications to the content dump.

There are two ways to perform the migration:

- An automated method of migration has been provided which uses a migrator Component to create the migration dump out of the old site (Mambo 4.5.x up to Joomla! 1.0.x) and a smart import facility in the Joomla! 1.5 Installation that performs required conversions and modifications during the installation process.
- Migration can be performed manually. This involves exporting the required tables, manually performing required conversions and modifications and then importing the content to the new site after it is installed.

## **Automated migration**

This is a two phased process using two tools. The first tool is a migration Component named com\_migrator. This Component has been contributed by Harald Baer and is based on his **eBackup** Component. The migrator needs to be installed on the old site and when activated it prepares the required export dump of the old site's data. The second tool is built into the Joomla! 1.5 installation process. The exported content dump is loaded to the new site and all conversions and modification are performed on-the-fly.

### Step 1 - Using com\_migrator to export data from old site:

- Install the com\_migrator Component on the **old** site. It can be found at the JoomlaCode developers forge.
- Select the Component in the Component Menu of the Control Panel.
- Click on the **Dump it** icon. Three exported _gzipped_ export scripts will be created. The first is a complete backup of the old site. The second is the migration content of all core elements which will be imported to the new site. The third is a backup of all 3PD Component tables.
- Click on the download icon of the particular exports files needed and store locally.
- Multiple export sets can be created.
- The exported data is not modified in anyway and the original encoding is preserved. This makes the com\_migrator tool a recommended tool to use for manual migration as well.

### Step 2 - Using the migration facility to import and convert data during Joomla! 1.5 installation:

Note: This function requires the use of the _iconv_ function in PHP to convert encodings. If _iconv_ is not found a warning will be provided.

- In step 6 - Configuration select the 'Load Migration Script' option in the 'Load Sample Data, Restore or Migrate Backed Up Content' section of the page.
- Enter the table prefix used in the content dump. For example: 'jos\_' or 'site2\_' are acceptable values.
- Select the encoding of the dumped content in the dropdown list. This should be the encoding used on the pages of the old site. (As defined in the \_ISO variable in the language file or as seen in the browser page info/encoding/source)
- Browse the local host and select the migration export and click on **Upload and Execute**
- A success message should appear or alternately a listing of database errors
- Complete the other required fields in the Configuration step such as Site Name and Admin details and advance to the final step of installation. (Admin details will be ignored as the imported data will take priority. Please remember admin name and password from the old site)
