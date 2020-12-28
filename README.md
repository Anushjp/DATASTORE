DataStore
A file-based key-value data store that supports the basic CRD (create, read, and delete) operations. This data store is meant to be used as a local storage for one single process on one laptop. The data store can be exposed as a library to clients that can instantiate a class and work with the data store.

How to consume the DataStore library?
First create a project and add the DataStore dependency, then you will be able instantiate and use the DataStore for your project usecase. For now the DataStore is available as a jar dependency only. Click here to download the datastore.jar
Here's an example given below

/**
* Constructor initialize the DataStore with default storage location
*/
DataStore myDataStore = new DataStore();// default location will be "C:\Users\Public\Documents"


/**
* Constructor initialize the DataStore with given storage location
*
* @param filePath
*            the storage location path
*/
DataStore myDataStore = new DataStore(String filePath);//pass file location


/**
*
* Method to create an element in the DataStore
*
* @param key
*            The key of the element
* @param value
*            The value of the element
* @return status of the operation
*/
myDataStore.create(String key, JSONObject value);


/**
* Method to create an element in the DataStore
*
* @param key
*            The key of the element
* @param value
*            The value of the element
* @param timeToLive
*            Number of seconds after which the element is destroyed
* @return status of the operation
*/
myDataStore.create(String key, JSONObject value, int timeToLive);


/**
* Method to read an element from the DataStore
*
* @param key
*            The key of the element to read the element
* @return The value as type of JSONObject
*/
myDataStore.read(String key)


/**
* Method to delete an element from the DataStore
*
* @param key
*            The key of the element to read the element
* @return The status of the delete operation
*/
myDataStore.delete(String key)

Sample DataStore consumer
The sample DataStore consumer application is here DataStoreConsumer

The sample response of DataStore consumer application given below

=============================================================
========================CREATE ==============================
=============================================================
Create operation successful
Operation failed due to key already available
Operation failed due to key already available
Create operation successful
Operation failed due to key length exceeded the limit(32chars)
====================AFTER WAIT===============
Create operation successful
Operation failed due to key already available
Operation failed due to key already available
Operation failed due to key already available
=============================================================
==========================READ===============================
=============================================================
{"firstName":"ANUSH","lastName":"J","address":"CBE","age":"20"}
{"firstName":"ANUSH","lastName":"J","address":"CBE"}
Operation failed due to key not available
Operation failed due to key length exceeded the limit(32chars)
====================AFTER WAIT===============
Operation failed due to key not available
{"firstName":"ANUSH","lastName":"J","address":"CBE"}
=============================================================
========================DELETE ==============================
=============================================================
Operation failed due to key not available
Record deletion successful
Operation failed due to key not available
Operation failed due to key not available
Operation failed due to key length exceeded the limit(32chars)
Thank you!!!
