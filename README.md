# ![LOGO](logo.png) Slicebox **flow**ground Connector

## Description

A generated **flow**ground connector for the Slicebox API (version 2.0).

Generated from: https://api.apis.guru/v2/specs/slicebox.local/2.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:06+03:00

## API Description

Slicebox - safe sharing of medical images

## Authorization

This API does not require authorization.

## Actions

### anonymize the images corresponding to the supplied list of image IDs (each paired with a list of DICOM tag translation). This route corresponds to repeated use of the route /images/{id}/anonymize.

*Tags:* `Anonymization`

### get a list of anonymization keys, each specifying how vital DICOM attributes have been anonymized for a particular image

*Tags:* `Anonymization`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of anonymization keys
* `count` - _optional_ - size of returned slice of anonymization keys
* `orderby` - _optional_ - property to order results by
* `orderascending` - _optional_ - order result ascendingly if true, descendingly otherwise
* `filter` - _optional_ - filter the results by matching substrings of properties against this value

### export all anonymization keys as a csv file

*Tags:* `Anonymization`

### submit a query for anonymization keys

*Tags:* `Anonymization`

### delete an anonymization key that is no longer of interest

*Tags:* `Anonymization`

#### Input Parameters
* `id` - _required_ - ID of anonymization key

### get the anonymization key with the supplied ID

*Tags:* `Anonymization`

#### Input Parameters
* `id` - _required_ - ID of anonymization key

### get pointers to the images corresponding to the anonymization key with the supplied ID

*Tags:* `Anonymization`

#### Input Parameters
* `id` - _required_ - ID of anonymization key

### list all supported anonymization options defining an anonymization profile

*Tags:* `Anonymization`

### get a list of box connections

*Tags:* `Boxes`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of boxes
* `count` - _optional_ - size of returned slice of boxes

### connect to another box using a received URL. Used to connect to a public box.

*Tags:* `Boxes`

### create a new box connection where the supplied entity holds the remote box name. Used by publicly available boxes.

*Tags:* `Boxes`

### get incoming transactions (finished, currently receiving, waiting or failed)

*Tags:* `Boxes`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of transactions
* `count` - _optional_ - size of returned slice of transactions

### delete an incoming transaction. If a currently active transaction is deleted, a new transaction with the remainder of the images is created when receiving the next incoming image.

*Tags:* `Boxes`

#### Input Parameters
* `id` - _required_ - ID of incoming transaction

### get the received images corresponding to the incoming transaction with the supplied ID

*Tags:* `Boxes`

#### Input Parameters
* `id` - _required_ - ID of incoming transaction

### get outgoing transactions (finished, currently sending, waiting or failed)

*Tags:* `Boxes`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of transactions
* `count` - _optional_ - size of returned slice of transactions

### delete an outgoing transaction. This will stop ongoing transactions.

*Tags:* `Boxes`

#### Input Parameters
* `id` - _required_ - ID of outgoing transaction

### get the sent images corresponding to the outgoing transaction with the supplied ID

*Tags:* `Boxes`

#### Input Parameters
* `id` - _required_ - ID of outgoing transaction

### Delete the remote box with the supplied ID

*Tags:* `Boxes`

#### Input Parameters
* `id` - _required_ - ID of box to remove

### send images corresponding to the supplied image ids to the remote box with the supplied ID

*Tags:* `Boxes`

#### Input Parameters
* `id` - _required_ - ID of box to send images to

### Returns a list of currently available destinations. Possible destinations are box - sending data to a remote box, and scu - sending data a receiving SCP.

*Tags:* `General`

### get a list of watch directories. Each watch directory and its sub-directories are watched for incoming DICOM files, which are read and imported into slicebox.

*Tags:* `Directories`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of watched directories
* `count` - _optional_ - size of returned slice of watched directories

### add a new directory to watch for incoming DICOM files

*Tags:* `Directories`

### stop watching and remove the directory corresponding to the supplied ID

*Tags:* `Directories`

#### Input Parameters
* `id` - _required_ - id of directory to stop watching

### Get a list of source to filter associations.

*Tags:* `Filtering`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of source <-> filter associations
* `count` - _optional_ - size of returned slice of source <-> filter associations

### Inserts or updates a source <-> filter associations. If the specified Source already  has an association this is updated, otherwise a new is inserted.

*Tags:* `Filtering`

### remove the source <-> filter association corresponding to the supplied ID

*Tags:* `Filtering`

#### Input Parameters
* `id` - _required_ - id of source <-> filter association to remove

### List defined filters

*Tags:* `Filtering`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of filters
* `count` - _optional_ - size of returned slice of filters

### Inserts or updates a filter. If a filter with same name as supplied filter exists this filter is updated, otherwise a new filter is inserted.

*Tags:* `Filtering`

### remove the filter corresponding to the supplied ID

*Tags:* `Filtering`

#### Input Parameters
* `id` - _required_ - id of filter to remove

### List tagpaths for the selected filter

*Tags:* `Filtering`

#### Input Parameters
* `id` - _required_ - id of filter

### add a tagpath to a filter

*Tags:* `Filtering`

#### Input Parameters
* `id` - _required_ - id of filter to remove

### remove the tagpath corresponding to the supplied ID

*Tags:* `Filtering`

#### Input Parameters
* `id` - _required_ - id of filter
* `tagpathid` - _required_ - id of TagPath to remove

### remove the forwarding rule corresponding to the supplied ID

*Tags:* `Forwarding`

#### Input Parameters
* `id` - _required_ - id of forwarding rule to remove

### get a list of all forwarding rules. A forwarding rule specifies the automatic forwarding of images from a source (SCP, BOX, etc.) to a destimation (BOX, SCU, etc.)

*Tags:* `Forwarding`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of rules
* `count` - _optional_ - size of returned slice of rules

### add a new forwarding rule

*Tags:* `Forwarding`

### add a DICOM dataset to slicebox

*Tags:* `Images`

### bulk delete a sequence of images according to the supplied image IDs. This is the same as a sequence of DELETE requests to /images/{id}

*Tags:* `Images`

### download the export set with the supplied export set ID as a zip archive

*Tags:* `Images`

#### Input Parameters
* `id` - _required_ - ID of export set to download

### create an export set, a group of image IDs of images to export. The export set will contain the selected images. The export set is available for download 12 hours before it is automatically deleted.

*Tags:* `Images`

### add a JPEG image to slicebox. The image data will be wrapped in a DICOM file and added as a new series belonging to the study with the supplied ID

*Tags:* `Images`

#### Input Parameters
* `studyid` - _required_ - ID of study to add new series to
* `description` - _optional_ - DICOM series description of the resulting secondary capture series

### Delete the image with the supplied ID

*Tags:* `Images`

#### Input Parameters
* `id` - _required_ - ID of image

### fetch dataset corresponding to the supplied image ID

*Tags:* `Images`

#### Input Parameters
* `id` - _required_ - ID of image

### delete the selected image and replace it with an anonymized version

*Tags:* `Anonymization` `Images`

#### Input Parameters
* `id` - _required_ - ID of image to anonymize

### get an anonymized version of the image with the supplied ID

*Tags:* `Anonymization` `Images`

#### Input Parameters
* `id` - _required_ - ID of image for which to get anonymized dataset

### list all DICOM attributes of the dataset corresponding to the supplied image ID

*Tags:* `Images`

#### Input Parameters
* `id` - _required_ - ID of image

### get basic information about the pixel data of an image

*Tags:* `Images`

#### Input Parameters
* `id` - _required_ - ID of image

### modify and/or insert image attributes according to the input tagpath-value mappings

*Tags:* `Images`

#### Input Parameters
* `id` - _required_ - ID of image to modify

### get a PNG image representation of the image corresponding to the supplied ID

*Tags:* `Images`

#### Input Parameters
* `id` - _required_ - ID of image
* `framenumber` - _optional_ - frame/slice to show
* `windowmin` - _optional_ - intensity window minimum value. If not specified or set to zero, windowing will be selected from relevant DICOM attributes
* `windowmax` - _optional_ - intensity window maximum value. If not specified or set to zero, windowing will be selected from relevant DICOM attributes
* `imageheight` - _optional_ - height of PNG image. If not specified or set to zero, the image height will equal that of the data

### Returns a list of available import sessions.

*Tags:* `Import`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of import sessions
* `count` - _optional_ - size of returned slice of import sessions

### create a new import sessions

*Tags:* `Import`

### deletes the import session with the supplied ID

*Tags:* `Import`

#### Input Parameters
* `id` - _required_ - ID of import session to delete

### Returns the import sessions with the supplied ID

*Tags:* `Import`

#### Input Parameters
* `id` - _required_ - ID of session

### get the imported images corresponding to the import session with the supplied ID

*Tags:* `Import`

#### Input Parameters
* `id` - _required_ - ID of import session

### add a DICOM dataset to the import session with the supplied ID

*Tags:* `Import`

#### Input Parameters
* `id` - _required_ - ID of session

### delete all log messages

*Tags:* `Logs`

### get a list of slicebox log messages

*Tags:* `Logs`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of log messages
* `count` - _optional_ - size of returned slice of log messages
* `subject` - _optional_ - log subject to filter results by
* `type` - _optional_ - log type (DEFAULT, INFO, WARN, ERROR) to filter results by

### Delete the log entry with the supplied ID

*Tags:* `Logs`

#### Input Parameters
* `id` - _required_ - ID of log entry

### Returns a list of flattened metadata on the patient, study and series levels

*Tags:* `Meta Data`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of flat series
* `count` - _optional_ - size of returned slice of flat series
* `orderby` - _optional_ - flat series property to order results by
* `orderascending` - _optional_ - order result ascendingly if true, descendingly otherwise
* `filter` - _optional_ - filter the results by matching substrings of flat series properties against this value
* `sources` - _optional_ - filter the results by matching on one or more series sources. Examples of sources are user, box, directory or scp. The list of sources to filter results by must have the form TYPE1:ID1,TYPE2:ID2,...,TYPEN:IDN. For instance, the argument sources=box:1,user:5 shows results either sent from (slice)box with id 1 or uploaded by user with id 5.
* `seriestypes` - _optional_ - filter the results by matching on one or more series types. The supplied list of series types must be a comma separated list of series type ids. For instance, the argument seriestypes=3,7,22 shows series assigned to either of the series types with ids 3, 7 and 22.
* `seriestags` - _optional_ - filter the results by matching on one or more series tags. The supplied list of series tags must be a comma separated list of series tag ids. For instance, the argument seriestags=6,2,11 shows series with either of the series tags with ids 6, 2 and 11.

### submit a query for flat series

*Tags:* `Meta Data`

### Return the flat series with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of flat series

### Returns a list of metadata on the image level of the DICOM hierarchy

*Tags:* `Meta Data`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of images
* `count` - _optional_ - size of returned slice of images
* `seriesid` - _required_ - reference to series to list images for

### submit a query for images

*Tags:* `Meta Data`

### Return the image with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of image

### Returns a list of metadata on the patient level of the DICOM hierarchy

*Tags:* `Meta Data`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of patients
* `count` - _optional_ - size of returned slice of patients
* `orderby` - _optional_ - patient property to order results by
* `orderascending` - _optional_ - order result ascendingly if true, descendingly otherwise
* `filter` - _optional_ - filter the results by matching substrings of patient properties against this value
* `sources` - _optional_ - filter the results by matching on one or more underlying series sources. Examples of sources are user, box, directory or scp. The list of sources to filter results by must have the form TYPE1:ID1,TYPE2:ID2,...,TYPEN:IDN. For instance, the argument sources=box:1,user:5 shows results either sent from (slice)box with id 1 or uploaded by user with id 5.
* `seriestypes` - _optional_ - filter the results by matching on one or more underlying series types. The supplied list of series types must be a comma separated list of series type ids. For instance, the argument seriestypes=3,7,22 shows results including series assigned to either of the series types with ids 3, 7 and 22.
* `seriestags` - _optional_ - filter the results by matching on one or more underlying series tags. The supplied list of series tags must be a comma separated list of series tag ids. For instance, the argument seriestags=6,2,11 shows results including series with either of the series tags with ids 6, 2 and 11.

### submit a query for patients

*Tags:* `Meta Data`

### Return the patient with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of patient

### Returns all images for the patient with the supplied patient ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of patient
* `sources` - _optional_ - filter the results by matching on one or more series sources. Examples of sources are user, box, directory or scp. The list of sources to filter results by must have the form TYPE1:ID1,TYPE2:ID2,...,TYPEN:IDN. For instance, the argument sources=box:1,user:5 shows results either sent from (slice)box with id 1 or uploaded by user with id 5.
* `seriestypes` - _optional_ - filter the results by matching on one or more series types. The supplied list of series types must be a comma separated list of series type ids. For instance, the argument seriestypes=3,7,22 shows series assigned to either of the series types with ids 3, 7 and 22.
* `seriestags` - _optional_ - filter the results by matching on one or more series tags. The supplied list of series tags must be a comma separated list of series tag ids. For instance, the argument seriestags=6,2,11 shows series with either of the series tags with ids 6, 2 and 11.

### Returns a list of metadata on the series level of the DICOM hierarchy

*Tags:* `Meta Data`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of series
* `count` - _optional_ - size of returned slice of series
* `studyid` - _required_ - reference to study to list series for
* `sources` - _optional_ - filter the results by matching on one or more series sources. Examples of sources are user, box, directory or scp. The list of sources to filter results by must have the form TYPE1:ID1,TYPE2:ID2,...,TYPEN:IDN. For instance, the argument sources=box:1,user:5 shows results either sent from (slice)box with id 1 or uploaded by user with id 5.
* `seriestypes` - _optional_ - filter the results by matching on one or more series types. The supplied list of series types must be a comma separated list of series type ids. For instance, the argument seriestypes=3,7,22 shows series assigned to either of the series types with ids 3, 7 and 22.
* `seriestags` - _optional_ - filter the results by matching on one or more series tags. The supplied list of series tags must be a comma separated list of series tag ids. For instance, the argument seriestags=6,2,11 shows series with either of the series tags with ids 6, 2 and 11.

### submit a query for series

*Tags:* `Meta Data`

### Return the series with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of series

### get the list of series tags for the series with the supplied ID.

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of series

### add a series tag to the series with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of series

### Delete all series types for the series with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of series

### get the list of series types for the series with the supplied ID.

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of series

### Return the source of the series with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of series

### Delete the series tag with the supplied series tag ID from the series with the supplied series ID

*Tags:* `Meta Data`

#### Input Parameters
* `seriesId` - _required_ - ID of series
* `seriesTagId` - _required_ - ID of series tag to remove

### Delete the series type with the supplied series type ID from the series with the supplied series ID

*Tags:* `Meta Data`

#### Input Parameters
* `seriesId` - _required_ - ID of series
* `seriesTypeId` - _required_ - ID of series type to remove

### Add the series type with the supplied series type ID to the series with the supplied series ID

*Tags:* `Meta Data`

#### Input Parameters
* `seriesId` - _required_ - ID of series
* `seriesTypeId` - _required_ - ID of series type to add

### Returns a list of series tags currently currently in use.

*Tags:* `Meta Data`

### Returns a list of metadata on the study level of the DICOM hierarchy

*Tags:* `Meta Data`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of studies
* `count` - _optional_ - size of returned slice of studies
* `patientid` - _required_ - reference to patient to list studies for
* `sources` - _optional_ - filter the results by matching on one or more underlying series sources. Examples of sources are user, box, directory or scp. The list of sources to filter results by must have the form TYPE1:ID1,TYPE2:ID2,...,TYPEN:IDN. For instance, the argument sources=box:1,user:5 shows results either sent from (slice)box with id 1 or uploaded by user with id 5.
* `seriestypes` - _optional_ - filter the results by matching on one or more underlying series types. The supplied list of series types must be a comma separated list of series type ids. For instance, the argument seriestypes=3,7,22 shows results including series assigned to either of the series types with ids 3, 7 and 22.
* `seriestags` - _optional_ - filter the results by matching on one or more underlying series tags. The supplied list of series tags must be a comma separated list of series tag ids. For instance, the argument seriestags=6,2,11 shows results including series with either of the series tags with ids 6, 2 and 11.

### submit a query for studies

*Tags:* `Meta Data`

### Return the study with the supplied ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of study

### Returns all images for the study with the supplied study ID

*Tags:* `Meta Data`

#### Input Parameters
* `id` - _required_ - ID of study
* `sources` - _optional_ - filter the results by matching on one or more series sources. Examples of sources are user, box, directory or scp. The list of sources to filter results by must have the form TYPE1:ID1,TYPE2:ID2,...,TYPEN:IDN. For instance, the argument sources=box:1,user:5 shows results either sent from (slice)box with id 1 or uploaded by user with id 5.
* `seriestypes` - _optional_ - filter the results by matching on one or more series types. The supplied list of series types must be a comma separated list of series type ids. For instance, the argument seriestypes=3,7,22 shows series assigned to either of the series types with ids 3, 7 and 22.
* `seriestags` - _optional_ - filter the results by matching on one or more series tags. The supplied list of series tags must be a comma separated list of series tag ids. For instance, the argument seriestags=6,2,11 shows series with either of the series tags with ids 6, 2 and 11.

### get a list of DICOM SCPs. Each SCP is a server for receiving DICOM images from e.g. a PACS system.

*Tags:* `SCPs`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of SCPs
* `count` - _optional_ - size of returned slice of SCPs

### add a new SCP for receiving DICOM images

*Tags:* `SCPs`

### shut down and remove the SCP corresponding to the supplied ID

*Tags:* `SCPs`

#### Input Parameters
* `id` - _required_ - id of SCP to remove

### get a list of DICOM SCUs. Each SCU is a client for sending DICOM images to an SCP, e.g. a PACS system.

*Tags:* `SCUs`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of SCUs
* `count` - _optional_ - size of returned slice of SCUs

### add a new SCU for sending DICOM images

*Tags:* `SCUs`

### remove the SCU corresponding to the supplied ID

*Tags:* `SCUs`

#### Input Parameters
* `id` - _required_ - id of SCU to remove

### send the images with the supplied image IDs to a DICOM SCP using the the SCU with the supplied scu ID

*Tags:* `SCUs`

#### Input Parameters
* `id` - _required_ - id of SCU to use for sending

### get a list of all added series types. By filtering search results for certain series types, it is easier for applications to ensure that they read images of applicable types.

*Tags:* `Series Types`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of series types
* `count` - _optional_ - size of returned slice of series types

### add a new series type

*Tags:* `Series Types`

### get a list of rules for assigning series types to series. A rule connects to a series of attributes with values and a resulting series type. If a series has the required values of the listed attributes, it is assigned to the series type of the rule.

*Tags:* `Series Types`

#### Input Parameters
* `seriestypeid` - _required_ - ID of series type to list rules for

### add a new series type rule

*Tags:* `Series Types`

### get the status of the internal process of updating series types for series following a change of series types, rules or attributes.

*Tags:* `Series Types`

### remove the series type rule corresponding to the supplied ID

*Tags:* `Series Types`

#### Input Parameters
* `id` - _required_ - id of series type rule to remove

### get the list of attributes for the series type rule with the supplied ID.

*Tags:* `Series Types`

#### Input Parameters
* `id` - _required_ - index of series type rule to list rule attributes for

### add a new series type rule attribute

*Tags:* `Series Types`

#### Input Parameters
* `id` - _required_ - ID of rule

### remove the series type rule attribute corresponding to the supplied series type and attribute IDs

*Tags:* `Series Types`

#### Input Parameters
* `ruleId` - _required_ - id of series type rule for which to remove an attribute
* `attributeId` - _required_ - id of attribute to remove

### submit a query for seriestypes for a list of series

*Tags:* `Meta Data`

### remove the series type corresponding to the supplied ID

*Tags:* `Series Types`

#### Input Parameters
* `id` - _required_ - id of series type to remove

### request an asynchronous update of all series, labelling appropriate series with the series type corresponding to the supplied ID.

*Tags:* `Series Types`

#### Input Parameters
* `id` - _required_ - id of series type to update series labels for

### Returns a list of currently available data sources. Possible source types are user - data imported by an API call by a user, box - data received from a remote box, directory - data imported via a watched directory, import - data imported into slicebox using import sessions, or scp - data received from a PACS.

*Tags:* `General`

### No-op route for checking whether the service is alive or not

*Tags:* `General`

### stop and shut down slicebox

*Tags:* `General`

### add an image (dataset) as part of a transaction. This method is used when sending images using the push method to a public slicebox.

*Tags:* `Transactions`

#### Input Parameters
* `token` - _required_ - authentication token identifying the current box-to-box connection
* `transactionid` - _required_ - the ID of the client's outgoing transaction
* `sequencenumber` - _required_ - the index of this image in the transaction
* `totalimagecount` - _required_ - the total number of images in this transaction

### fetch an image from the connected box as part of a transaction. This method is used when sending images using the poll method from a public slicebox.

*Tags:* `Transactions`

#### Input Parameters
* `token` - _required_ - authentication token identifying the current box-to-box connection
* `transactionid` - _required_ - the ID of the outgoing transaction
* `imageid` - _required_ - the ID of the outgoing transaction image

### signal that the supplied outgoing transaction and image was successfully received and can be marked as sent. This method is used when sending images using the poll method from a public slicebox.

*Tags:* `Transactions`

#### Input Parameters
* `token` - _required_ - authentication token identifying the current box-to-box connection

### signal that the image corresponding to the supplied outgoing transaction and image could not be read or stored properly on the receiving side, and that the transaction should be marked as failed.

*Tags:* `Transactions`

#### Input Parameters
* `token` - _required_ - authentication token identifying the current box-to-box connection

### get next outgoing transaction and image (information on the next image that the connected box wishes to send to you), if any. This method is used when sending images using the poll method from a public slicebox.

*Tags:* `Transactions`

#### Input Parameters
* `token` - _required_ - authentication token identifying the current box-to-box connection

### get the status of the remote incoming transaction with the supplied transaction ID

*Tags:* `Transactions`

#### Input Parameters
* `token` - _required_ - authentication token identifying the current box-to-box connection
* `transactionid` - _required_ - the ID of the client's outgoing transaction

### update the status of the transaction with the supplied ID

*Tags:* `Transactions`

#### Input Parameters
* `token` - _required_ - authentication token identifying the current box-to-box connection
* `transactionid` - _required_ - the ID of the client's outgoing transaction

### Returns all users of slicebox

*Tags:* `Users`

#### Input Parameters
* `startindex` - _optional_ - start index of returned slice of users
* `count` - _optional_ - size of returned slice of users

### Creates a new user. Dupicates are accepted but not added.

*Tags:* `Users`

### obtain information on the currently logged in user as specified by the supplied session cookie, IP address and user agent.

*Tags:* `Users`

### Obtain a session cookie that can be used to authenticate future API calls from the present IP address and with the present user agent.

*Tags:* `Users`

### Logout the current user by responding with a delete cookie header removing the session cookie for this user.

*Tags:* `Users`

### deletes a single user based on the ID supplied

*Tags:* `Users`

#### Input Parameters
* `id` - _required_ - ID of user to delete

## License

**flow**ground :- Telekom iPaaS / slicebox-local-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
