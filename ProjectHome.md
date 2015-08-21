Ant Task for IBM Mq Messaging.

Current release has the following features:

  * Send messages

  * Read messages

  * Browse messages

  * Delete messages

  * Filtering with a RegExp

  * Filtering with a range date (putDateTime is used for comparing)

  * IBM Websphere MQ 7.5

  * Define MCAUSER (username/password)

  * SSL Authentication (Server and Client using Truststore and Keystore)

Below you can see the correct use of the parameters with the chosen action:

| **Parameter/Action** | **Clear** | **Browse** | **Read** | **Write** | **Default** | **Note** |
|:---------------------|:----------|:-----------|:---------|:----------|:------------|:---------|
| **action**           | M         | M          | M        | M         | n/d         | The action (clear, browse, read, write) |
| **host**             | M         | M          | M        | M         | n/d         | The hostname or IP address |
| **channel**          | M         | M          | M        | M         |n/d          | The channel of the Queue Manager|
| **queue**            | M         | M          | M        | M         | n/d         | The name of the queue |
| **port**             | O         | O          | O        | O         | _1414_      | The port of the Queue Manager |
| **qmgrName**         | O         | O          | O        | O         | _blank_     | The Queue Manager name |
| **ccsid**            | n/a       | O          | O        | O         | _1208_      | Coded Character Set Identifier. See the complete list of CCSID on [IBM](http://www-01.ibm.com/software/globalization/ccsid/ccsid_registered.html) site |
| **userID**           | O         | O          | O        | O         | null        | The username for MCAUSER |
| **password**         | O         | O          | O        | O         | null        | The password for MCAUSER |
| **trustStore**       | O         | O          | O        | O         | null        | The file of the trustStore (only for SSL authentication) |
| **trustStorePassword** | O         | O          | O        | O         | null        | The password of the trustStore (only for SSL authentication) |
| **keyStore**         | O         | O          | O        | O         | null        | The file of the keyStore (only for SSL authentication) |
| **keyStorePassword** | O         | O          | O        | O         | null        | The password of the keyStore (only for SSL authentication) |
| **sslCipherSuite**   | O         | O          | O        | O         | null        | The sslCipherSuite used from the channel. See the list [here](IBM_ssl_Cipher_Suite.md) (only for SSL authentication) |
| **failonerror**      | O         | O          | O        | O         | true        | In case of an Exception, it fails or not |
| **match**            | n/a       | O          | O        | n/a       | null        | RegExp for filtering messages. Only messages that match the RegExp are saved |
| **dateFormat**       | O         | O          | O        | n/a       | _yyyyMMddHHmmss.SSS_ | The format of the date of the two parameter 'dateFrom' and 'dateTo' |
| **dateFrom**         | O         | O          | O        | n/a       | null        | The range date 'from'. If the action is 'read', only messages that are in the range are saved but ALL the messages are consumed. If the action is 'browse', only messages that are in the range are saved. If the action is 'clear', only messages that are in the range are deleted.|
| **dateTo**           | O         | O          | O        | n/a       | null        | The range date 'to'.Only messages that  are in the range are saved |
| **format**           | n/a       | n/a        | n/a      | O         | MQSTR       | The IBM message format|
| **text**             | n/a       | n/a        | n/a      | O         | n/d         | The message text |
| **inputFile**        | n/a       | n/a        | n/a      | O         | n/d         | File containing the message to send to the queue |
| **inputEncoding**    | n/a       | n/a        | n/a      | O         | _UTF-8_     | Java Character Encoding |
| **listFile**         | n/a       | n/a        | n/a      | O         | n/d         | List of file to send to the queue |
| **fileset**          | n/a       | n/a        | n/a      | O         | n/d         | Multiple choose of file to read and send to the queue |
| **skipZeroLength**   | n/a       | n/a        | n/a      | O         | _false_     | If the file is empty, skip it |
| **outputFileName**   | n/a       | O          | O        | n/a       | n/d         | The path and the filename for each message. Automatically the task attach a counter (the index number in the queue) |
| **outputFileExt**    | n/a       | O          | O        | n/a       | n/d         | The extension of the file for each message |
| **OutputEncoding**   | n/a       | O          | O        | n/a       | _UTF-8_     | Java Character Encoding |
| **override**         | n/a       | O          | O        | n/a       | _false_     | Override if the output file exists |

M=Mandatory, O=Optional, n/a=Not Allowed, n/d=Not Defined

[![](http://www2.clustrmaps.com/stats/maps-no_clusters/code.google.com-p-anttaskmqseries--thumb.jpg)](http://www2.clustrmaps.com/user/57910a850)