# Description

POC in order to protect an document upload application feature against "malicious" document submission.

It's the code repository of this OWASP [article](https://www.owasp.org/index.php/Protect_FileUpload_Against_Malicious_File). 

# Note about dependencies not present into Maven repositories

Before to launch a build or execution of the POC, use the script **install-non-maven-deps.bat** to install dependencies into your local Maven cache.

# Build status

[![Build Status](https://travis-ci.org/righettod/document-upload-protection.svg?branch=master)](https://travis-ci.org/righettod/document-upload-protection)

# Run the POC

1) Use the maven command below to run the web container:

`mvn -DskipTests tomcat7:run-war`

2) Use the following URL to acces to upload form and use the POC:

`http://localhost:9090`

# Format supported

We will focus our work on the following formats because it's the formats that are often used as attack vector and also to transmit legit information: 

* Microsoft Word document (from 97 to 2016),

* Microsoft Excel document (from 97 to 2016),

* Microsoft Powerpoint document (from 97 to 2016),

* Adobe Pdf document,

* Image document (formats supported by the IJ API: http://rsb.info.nih.gov/ij/developer/api).

# Note on Word/Excel/Powerpoint API

The reason why Aspose API have been used into this POC are the following:

* There many way to embed Macro into a Microsoft Office document and, instead of manually support all the way that exists on the wild (they evolve every days), we prefer to use features from a company that perform R&D on these formats, precisely DOC/XLS/PPT native formats that are proprietary. 

* The open source API POI for DOC native format is not very stable.

* The open source API JEXCELAPI for XLS native format is not often maintained (last publishing on Maven repository date from 27-Nov-2012).

# Information links

* https://www.greyhathacker.net/?p=872
