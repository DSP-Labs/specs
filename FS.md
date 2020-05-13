# ![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) FS

FS is the low-level module to provide reliable file storage and efficient file management.  It is widly used in the DSP ecosystem by both storage clients and storage nodes for a variety of scenarios like file uploading, file downloading, and also file sharing.



## Block

The basic building element in the FS is the **Block**. 

A hash-based Block Identifier could be calculated from the Block data,  we call it Block Hash.

A Block can either be a data block whose main purpose is to store data or a non-data block who has no data stored but contains Block Hashes as links to other Blocks.

With a given Block and its Block Hash, it can be easily verified if the Block data has been corrupted. In this way Blocks can be distributed within the DSP with guarantee it's unchanged.



## File

A File can be chunked into Blocks with defined block size, and it can be saved in local storage with support of different underlying storage types ranging from flat files to KV databases like LevelDB.

The result of file chunking is a tree structure with a Root Block. The leaves of the tree contains the data of the file, and Root Block or other intermediate Blocks contains links to other Blocks. 

The chunking method is definitive so the Root Block Hash can be used to identify a specific file, we call it File Hash.



## Storage Management

**Block Sharing**

As mentioned above, a File in the FS is organized as a tree with links to Blocks. It is possible that different files could have some Blocks in common. In the FS, there is only one copy of the Block is saved in storage, and the Block is shared by these files.

If one file is deleted, the shared block will not be deleted since it is still linked by other file. When all the links to the Block is gone, which means all files those have link to Block is removed from the FS, the Block can be deleted.

In this way, storage space could be greatly reduced if we have a lot of Blocks shared by files. 

**garbage collection**

An Mark-and-Sweep garbage collection mechanism is used to delete a Block that has no reference/link to it. When a file is deleted, its Root Block Hash will be dereferenced and all the Blocks that no longer referenced will be deleted in next garbage collection.

Garbage collection is costly since it needs to check all the reference/link for all Blocks. It should be performed with caution.

## FS API

FS API is provided by to facilitate application development based on FS. Some basic API is listed below:

**AddFile**

Add a file to FS after chunking into Blocks.

**DeleteFile**

Delete a file from FS.

**GetBlockHashesOfFile**

Returns all Blocks hashes of a file with a given File Hash.

**PutBlock**

Store a Block in the FS.

**GetBlock**

Get Block with given Hash from FS.

**GarbageCollect**

Manually trigger the garbage collector to remove all Blocks those have no reference/link to them.