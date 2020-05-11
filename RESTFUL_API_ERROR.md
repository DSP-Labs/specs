### Error Code 

| Error Code | Content | Meaning |
| ------ | ------------------------------------ | ------------------------------ |
| 0      |   SUCCESS                            | Success                        |
| 40001  | INTERNAL_ERROR                       | Internal Server Error          |
| 40002  | INVALID_PARAMS                       | Incorrect parameter (missing)  |
| 40003  | NO_DSP                               | Service not instantiated       |
| 40004  | NO_DB                                | Database initialization failed |
| 40005  | CONTRACT_ERROR                       | Contract call failed           |
| 40006  | INSUFFICIENT_BALANCE                 | Insufficient balance           |
| 40007  | NO_ACCOUNT                           | No account                     |
| 40008  | ACCOUNT_EXIST                        | Account already exists         |
| 40009  | NO_DNS                               | No DNS node connected          |
| 40010  | INVALID_WALLET_ADDRESS               | Wallet address is illegal      |
| 50000  | CHAIN_INTERNAL_ERROR                 | Internal error                 |
| 50001  | CHAIN_GET_HEIGHT_FAILED              | Failed to get current height   |
| 50002  | CHAIN_GET_BLK_BY_HEIGHT_FAILED       | Failed to get block            |
| 50003  | CHAIN_WAIT_TX_COMFIRMED_TIMEOUT      | Timeout waiting for transaction confirmation|
| 50004  | CHAIN_UNKNOWN_BLOCK                  | Unknown block |
| 50005  | CHAIN_UNKNOWN_TX                     | Unknown transaction |
| 50006  | CHAIN_UNKNOWN_SMARTCONTRACT          | Unknown contract |
| 50007  | CHAIN_UNKNOWN_SMARTCONTRACT_EVENT    | Unknown contract event |
| 50008  | CHAIN_UNKNOWN_ASSET                  | Unknown asset |
| 50009  | CHAIN_TRANSFER_ERROR                 | Transfer failed |
| 50013  | WALLET_FILE_NOT_EXIST                | Wallet file does not exist |
| 50014  | ACCOUNTDATA_NOT_EXIST                | Wallet account data does not exist |
| 50015  | ACCOUNT_PASSWORD_WRONG               | wrong password                       |
| 50016  | CREATE_ACCOUNT_FAILED                | Account creation failed |
| 50017  | ACCOUNT_EXPORT_FAILED                | Account export failed |
| 54001  | FS_GET_SETTING_FAILED                | Failed to obtain FS contract configuration |
| 54002  | FS_GET_USER_SPACE_FAILED             | Failed to obtain user space |
| 54003  | FS_GET_FILE_LIST_FAILED              | Failed to get file list |
| 54004  | FS_UPDATE_USERSPACE_FAILED           | Failed to update user space |
| 54005  | FS_CANT_REVOKE_OF_EXISTS_FILE        | Can't revoke space for storing files |
| 54006  | FS_NO_USER_SPACE_TO_REVOKE           | There is no room to revoke |
| 54007  | FS_USER_SPACE_SECOND_TOO_SMALL       | Increased seconds are too small |
| 54008  | FS_USER_SPACE_PERMISSION_DENIED      | No permission to update |
| 54009  | FS_UPLOAD_FILEPATH_ERROR             | Error in file upload path |
| 54010  | FS_UPLOAD_INTERVAL_TOO_SMALL         | The verification period for uploading calculated fee is too short |
| 54011  | FS_UPLOAD_GET_FILESIZE_FAILED        | Failed to calculate file fee to get file size |
| 54012  | FS_UPLOAD_CALC_FEE_FAILED            | Failed to calculate file fee |
| 55000  | DSP_INIT_FAILED                      | DSP initialization failed |
| 55001  | DSP_START_FAILED                     | DSP failed to start |
| 55002  | DSP_STOP_FAILED                      | DSP stop failed |
| 55010  | DSP_UPLOAD_FILE_FAILED               | File upload failed |
| 55011  | DSP_USER_SPACE_EXPIRED               | User space expired |
| 55012  | DSP_USER_SPACE_NOT_ENOUGH            | Insufficient user space |
| 55013  | DSP_UPLOAD_URL_EXIST                 | The file URL already exists |
| 55014  | DSP_DELETE_FILE_FAILED               | Failed to delete file |
| 55015  | DSP_CALC_UPLOAD_FEE_FAILED           | Failed to calculate upload cost |
| 55016  | DSP_GET_FILE_LINK_FAILED             | Failed to get file link |
| 55017  | DSP_ENCRYPTED_FILE_FAILED            | File encryption failed |
| 55018  | DSP_DECRYPTED_FILE_FAILED            | File decryption failed|
| 55019  | DSP_WHITELIST_OP_FAILED              | Whitelist operation failed|
| 55020  | DSP_GET_WHITELIST_FAILED             | Failed to get whitelist|
| 55021  | DSP_UPDATE_CONFIG_FAILED             | Failed to update system configuration|
| 55022  | DSP_UPLOAD_FILE_EXIST                | File uploaded|
| 55023  | DSP_PAUSE_UPLOAD_FAIELD              | Upload pause failed|
| 55024  | DSP_RESUME_UPLOAD_FAIELD             | Continue upload failure|
| 55025  | DSP_RETRY_UPLOAD_FAIELD              | Retry upload failed|
| 55026  | DSP_PAUSE_DOWNLOAD_FAIELD            | Failed to pause download|
| 55027  | DSP_RESUME_DOWNLOAD_FAIELD           | Continue download failed|
| 55028  | DSP_RETRY_DOWNLOAD_FAIELD            | Retry download failed|
| 55029  | DSP_CANCEL_TASK_FAILED               | Failed to cancel the task|
| 55030  | DSP_NODE_REGISTER_FAILED             | Node registration failed|
| 55031  | DSP_NODE_UNREGISTER_FAILED           | Node logout failed|
| 55032  | DSP_NODE_UPDATE_FAILED               | Node update failed|
| 55033  | DSP_NODE_WITHDRAW_FAILED             | Node withdrawal failed|
| 55034  | DSP_NODE_QUERY_FAILED                | Node query failed|
| 55040  | DSP_URL_REGISTER_FAILED              | URL registration failed|
| 55041  | DSP_URL_BIND_FAILED                  | URL binding failed|
| 55050  | DSP_DNS_REGISTER_FAILED              | DNS node registration failed|
| 55051  | DSP_DNS_UNREGISTER_FAILED            | DNS node logout failed|
| 55052  | DSP_DNS_UPDATE_FAILED                | DNS node update failed|
| 55053  | DSP_DNS_WITHDRAW_FAILED              | DNS node withdrawal failed|
| 55054  | DSP_DNS_QUIT_FAILED                  | DNS node exit failed|
| 55055  | DSP_DNS_ADDPOS_FAILED                | DNS node failed to add mortgage|
| 55056  | DSP_DNS_REDUCEPOS_FAILED             | DNS node failure to reduce mortgage|
| 55057  | DSP_DNS_GET_NODE_BY_ADDR             | Query DNS node failed|
| 55058  | DSP_DNS_QUERY_INFOS_FAILED           | Query all DNS node information failed      |
| 55059  | DSP_DNS_QUERY_INFO_FAILED            | Failed to query information about a single DNS node      |
| 55060  | DSP_DNS_QUERY_ALLINFOS_FAILED        | Query all DNS node information failed      |
| 55061  | DSP_DNS_GET_EXTERNALIP_FAILED        | Query DNS node to obtain IP information failed      |
| 55062  | DSP_USER_SPACE_PERIOD_NOT_ENOUGH     | Insufficient time in user space      |
| 55063  | DSP_CUSTOM_EXPIRED_NOT_ENOUGH        | Not enough storage time for upload settings      |
| 55100  | DSP_FILE_INFO_NOT_FOUND              | No file information found on the chain      |
| 55101  | DSP_FILE_NOT_EXISTS                  | file does not exist                           |
| 55102  | DSP_FILE_DECRYPTED_WRONG_PWD         | Wrong decryption password      |
| 56000  | DSP_CHANNEL_INTERNAL_ERROR           | Channel internal error      |
| 56001  | DSP_CHANNEL_OPEN_FAILED              | Failed to open channel      |
| 56002  | DSP_CHANNEL_CLOSE_FAILED             | Failed to close the channel      |
| 56003  | DSP_CHANNEL_QUERY_AVA_BALANCE_FAILED | Query channel available balance failed      |
| 56004  | DSP_CHANNEL_DEPOSIT_FAILED           | Channel recharge failed      |
| 56005  | DSP_CHANNEL_WITHDRAW_FAILED          | Channel withdrawal failed      |
| 56006  | DSP_CHANNEL_WITHDRAW_OVERFLOW        | Channel withdrawal cash amount error      |
| 56007  | DSP_CHANNEL_GET_ALL_FAILED           | Failed to get all channels      |
| 56008  | DSP_CHANNEL_MEDIATRANSFER_FAILED     | Routing payment failed      |
| 56009  | DSP_CHANNEL_CO_SETTLE_FAILED         | Cooperation close failed      |
| 56010  | DSP_CHANNEL_INIT_NOT_FINISH          | Channel instantiation is not complete      |
| 56011  | DSP_CHANNEL_EXIST                    | Channel already exists      |
| 56012  | DSP_CHANNEL_DOWNLOAD_DNS_NOT_EXIST   | Cannot download without connecting to a DNS node      |
| 56013  | DSP_CHANNEL_BALANCE_DNS_NOT_ENOUGH   | DNS node balance is insufficient to download      |
| 56014  | DSP_CHANNEL_WITHDRAW_WRONG_AMOUNT    | Channel withdraw cash amount is wrong      |
| 56015  | DSP_CHANNEL_SYNCING                  | Channel is syncing blocks      |
| 58000  | DSP_TASK_NOT_EXIST                   | Operational task does not exist      |
| 59000  | DB_FIND_SHARE_RECORDS_FAILED         | Database query sharing revenue failed      |
| 59001  | DB_SUM_SHARE_PROFIT_FAILED           | Database statistics sharing revenue failure      |
| 59002  | DB_FIND_USER_SPACE_RECORD_FAILED     | Database query adjustment space record lost败     |
| 59003  | DB_ADD_USER_SPACE_RECORD_FAILED      | Database addition adjustment space record is missing败     |
| 59004  | DB_GET_FILEINFO_FAILED               | Failed to obtain file information      |
| 59100  | NET_RECONNECT_PEER_FAILED            | Node reconnection failed      |





### Transmission list interface error code

| Error Code | Content | Meaning                                |
| ------ | ----------------------------------- | ----------------------------------- |
| 40000  | INVALID_PARAMS                      |The parameter is wrong|
| 40001  | INTERNAL_ERROR                      |internal error                           |
| 50000  | NEW_TASK_FAILED                     |Failed to create task|
| 50001  | PREPARE_UPLOAD_ERROR                |Abnormal data processing before uploading|
| 50002  | TASK_INTERNAL_ERROR                 |Abnormal task|
| 50003  | UPLOAD_TASK_EXIST                   |Upload task already exists|
| 50004  | SHARDING_FAIELD                     |Sharding failed|
| 50005  | FILE_HAS_UPLOADED                   |The file has been uploaded|
| 50006  | GET_STORAGE_NODES_FAILED            |Failed to obtain storage node|
| 50007  | ONLINE_NODES_NOT_ENOUGH             |The number of storage nodes in the entire network is insufficient|
| 50008  | PAY_FOR_STORE_FILE_FAILED           |File upload failed|
| 50009  | SET_FILEINFO_DB_ERROR               |File database save failed|
| 50010  | ADD_WHITELIST_ERROR                 |Failed to add whitelist|
| 50011  | GET_PDP_PARAMS_ERROR                |Failed to obtain PDP proof parameters|
| 50012  | GET_ALL_BLOCK_ERROR                 |Abnormal access to file block data|
| 50013  | SEARCH_RECEIVERS_FAILED             |Failed to find storage node|
| 50014  | RECEIVERS_NOT_ENOUGH                |Insufficient number of online storage nodes|
| 50015  | RECEIVERS_REJECTED                  |Storage node refuses to respond|
| 50016  | TASK_WAIT_TIMEOUT                   |Task wait timeout|
| 50017  | FILE_UPLOADED_CHECK_PDP_FAILED      |The file has been uploaded and the storage node fails to submit the PDP certificate|
| 50018  | GET_SESSION_ID_FAILED               |Failed to obtain SessionID|
| 50019  | FILE_UNIT_PRICE_ERROR               |File download price is abnormal|
| 50020  | TOO_MANY_TASKS                      |The task has reached the limit|
| 50021  | FILE_NOT_FOUND_FROM_CHAIN           |File information chain does not exist|
| 50022  | DOWNLOAD_REFUSED                    |Download rejected|
| 50023  | CHAIN_ERROR                         |Abnormal main chain request|
| 50024  | TASK_PAUSE_ERROR                    |Task pause failed|
| 50025  | GET_FILEINFO_FROM_DB_ERROR          |Failed to get file information from database|
| 50026  | DOWNLOAD_FILEHASH_NOT_FOUND         |File Hash not found|
| 50027  | NO_CONNECTED_DNS                    |No DNS connected|
| 50028  | NO_DOWNLOAD_SEED                    |No downloadable data source|
| 50029  | GET_DOWNLOAD_INFO_FAILED_FROM_PEERS |Failed to obtain information from the download node|
| 50030  | PREPARE_CHANNEL_ERROR               |Failed to prepare Channel before downloading|
| 50031  | FILEINFO_NOT_EXIST                  |File information does not exist|
| 50032  | PAY_UNPAID_BLOCK_FAILED             |Failed to pay for unpaid file blocks|
| 50033  | CREATE_DOWNLOAD_FILE_FAILED         |Failed to create download file|
| 50034  | GET_UNDOWNLOAD_BLOCK_FAILED         |Failed to get undownloaded file block|
| 50035  | DOWNLOAD_BLOCK_FAILED               |Failed to download file block|
| 50036  | GET_FILE_STATE_ERROR                |Failed to obtain file information|
| 50037  | WRITE_FILE_DATA_FAILED              |Failed to write data to file|
| 50038  | FS_PUT_BLOCK_FAILED                 |Failed to save file block to FS|
| 50039  | ADD_GET_BLOCK_REQUEST_FAILED        |Failed to add request file block task|
| 50040  | DECRYPT_FILE_FAILED                 |Decryption failed|
| 50041  | RENAME_FILED_FAILED                 |File rename failed|
| 50042  | DOWNLOAD_FILE_TIMEOUT               |File download timeout|
| 50043  | DOWNLOAD_FILE_RESUSED               |Download file refused|
| 50044  | UNITPRICE_ERROR                     |Failed to get file download unit price|
| 50045  | DOWNLOAD_TASK_EXIST                 |Download task already exists|
| 50046  | DECRYPT_WRONG_PASSWORD              |Wrong decryption password|
| 50047  | DELETE_FILE_HASHES_EMPTY            |Deleted file Hash is empty|
| 50048  | NO_FILE_NEED_DELETED                |No files need to be deleted|
| 50049  | DELETE_FILE_ACCESS_DENIED           |No permission to delete files|





### Code of the transmission process

| Status code | Content | Meaning          |
| ------ | --------------------------------- | ----------------------------------- |
| 0      | None                              |None|
| 1      | TaskPause                         |Task pause|
| 2      | TaskDoing                         |Mission continues|
| 3      | TaskUploadFileMakeSlice           |Start sharding|
| 4      | TaskUploadFileMakeSliceDone       |Sharding completed|
| 5      | TaskUploadFilePaying              |Payment on the chain|
| 6      | TaskUploadFilePayingDone          |Payment on chain completed|
| 7      | TaskUploadFileCommitWhitelist     |Submit whitelist information|
| 8      | TaskUploadFileCommitWhitelistDone |Complete whitelist information submission|
| 9      | TaskUploadFileFindReceivers       |Find storage nodes|
| 10     | TaskUploadFileFindReceiversDone   |Finding the storage node is complete|
| 11     | TaskUploadFileGeneratePDPData     |Generate PDP certification data|
| 12     | TaskUploadFileTransferBlocks      |Start transferring file block data|
| 13     | TaskUploadFileTransferBlocksDone  |Transfer file block data is complete|
| 14     | TaskUploadFileWaitForPDPProve     |Waiting for storage node to submit PDP certificate|
| 15     | TaskUploadFileWaitForPDPProveDone |The storage node submits the PDP certificate to complete|
| 16     | TaskUploadFileRegisterDNS         |Register information to DNS node|
| 17     | TaskUploadFileRegisterDNSDone     |Registration information is completed to the DNS node|
| 18     | TaskDownloadFileStart             |Start downloading files|
| 19     | TaskDownloadSearchPeers           |Find nodes for download|
| 20     | TaskDownloadFileDownloading       |File downloading|
| 21     | TaskDownloadRequestBlocks         |Download data block|
| 22     | TaskDownloadReceiveBlocks         |Data block received|
| 23     | TaskDownloadPayForBlocks          |Pay the download fee for the data block|
| 24     | TaskDownloadPayForBlocksDone      |Complete the download fee for the data block|
| 25     | TaskDownloadFileMakeSeed          |File download is complete, submit sharing information to DNS node|