# couchbase-fs-daemon
Is the Accesspoint for the Data Stored inside of a couchbase-fs-server

## AppPackage
You can Download and run the AppPackage directly on your server 

## Docker

## Installation on a System with NodeJS Installed

## USE via CLI

## USE via GUI

## Core Data Structure for Couchbase FileSystem

Because of the MetaFileSystem approch we are taking a file needs only meta-key's 
- keyprefixs: file-key, meta-key
- every file Entry in couchbase fs consists of 2 parts a file-key optional and a meta-key that is required

a file-key has only 2 key filds called data and formart all other meta goes into the meta-keys for that file-key
for chunked data we have formart.chunked === true that indicated that there are file-key-num entrys and allows more easy fetching of big files. It makes less sense to store big files in this filesystem as it will disable some futures like deduplication that is a build in future of couchbase-fs

```js
{
formart:
data:
}
```


## Manage Credentials
in many cases you probally want to use and supply credentials for example to use them with your protocol definitions in your meta-key's

there are millions of ways to solve that this needs evaluation we have some opinionated ways to do that but your free

## Exports
couchbase-fs supports exports to messagepack/zlib and clear text json
they can be stored anywhere on a filesystem or cloud to be more save you should maybe crypto them befor uploading them to the cloud via couchbase-fs-crypto that can store crypted data directly into couchbase-fs if that gets exported its still save.
