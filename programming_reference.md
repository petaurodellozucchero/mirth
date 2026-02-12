# Mirth

## ®

# Connect

# Programming Reference

Document Version 3.

October 2021



©2009-2021 NextGen Healthcare, Inc. i nextgen.com

**Legal Notice**

Mirth® Connect Programming Reference, document version 3.

Copyright © 2009- 2021 NextGen Healthcare, Inc. All rights reserved.

This book is provided as part of the Mirth Connect Fundamentals Training, Mirth Connect Fundamentals

Certification Training, Mirth Connect Advanced Training, or Mirth Connect Advanced Certification Training

course for the sole purpose of the attendee’s personal training use. It is not available for sale or resale apart

from attending one of the aforementioned training classes hosted by NextGen Healthcare, Inc.

This document may not to be distributed, reproduced, transmitted, published or modified in any manor

without the express written permission of NextGen Healthcare, Inc.

All names, logos, images and marks appearing within these materials, except as otherwise noted, are

trademarks owned or used under license by NextGen Healthcare, Inc. The use or misuse of these

trademarks or any other content is strictly prohibited.

The information in this book is to be used strictly for training purposes only. Neither NextGen Healthcare,

Inc. nor the author of this book assume any responsibility for any errors or omissions, or for damages

resulting from the use of the information contained herein.



## ©2009-2021 NextGen Healthcare, Inc. iii nextgen.com

- Predefined Global Variables Contents
- Available Destination Mappings
- Available Source Map Variables
- Available Alert Variables
- User API Java Classes
   - ACKGenerator
   - AlertSender
   - Attachment
   - Atta chmentUtil
   - AuthenticationResult
   - ChannelUtil
   - DatabaseConnection
   - DatabaseConnectionFactory
   - DateUtil
   - DestinationSet
   - DICOMUtil
   - FileUtil
   - ImmutableConnectorMessage
   - ImmutableMessage
   - ListBuilder
   - Lists
   - MapBuilder
   - Maps
   - MessageHeaders
   - MessageParameters
   - Response
   - ResponseFactory
   - SerializerFactory
   - SMTPConnection
   - SMTPConnectionFactory
   - VMRouter
- Standard Library Java Classes
- JavaScript E4X Classes
- Built-in Code Template JavaScript Functions
- Date/Time Formats
- Common MIME Types
- Common Email Headers


## Predefined Global Variables

**Variable Summary**

channelMap An instance of User API Java class
com.mirth.connect.server.userutil.ChannelMap, available in the scope of
each channel
void put(String key, Object value)
Inserts the value associated with the key in the map.
Object get(String key)
Returns the value
configurationMap An unmodifiable (read-only) instance of java.util.HashMap, available in
the entire scope of Mirth Connect. Used to store values for configuration
settings.
Object get(String key)
Returns the value
connectorMap An instance of java.util.HashMap, available in the scope of each
connector of each channel
void put(String key, Object value)
Inserts the value associated with the key in the map.
Object get(String key)
Returns the value
globalChannelMap An instance of
com.mirth.connect.server.util.GlobalChannelVariableStore encapsulating
java.util.HashMap. Available in the entire scope of a channel
void put(String key, Object value)
Inserts the value associated with the key in the map.
Object get(String key)
Returns the value
globalMap An instance of com.mirth.connect.server.util.GlobalVariableStore
encapsulating java.util.Has hMap. Available in the entire scope of Mirth
Connect.
void put(String key, Object value)
Inserts the value associated with the key in the map.
Object get(String key)
Returns the value
responseMap An instance of User API Java class
com.mirth.connect.server.userutil.ResponseMap , available in the scope
of each channel
void put(String key, Object value)
Inserts the value associated with the key in the map.
Object get(String key)
Returns the value
sourceMap An unmodifiable (read-only) instance of java.util.HashMap, available in
the scope of each channel
Object get(String key)
Returns the value
destinationSet An instance of User API Java class
com.mirth.connect.server.userutil.DestinationSet that
allows modification of the set of destinations to which the message
should be sent. Available only in the source transformer. Refer to the
User API Java Classes section for the summary of available methods.


logger An instance of org.apache.log4j.Logger available in the entire
scope of Connect.
void error(String errorMessage)
Prints the user-specified error message in mirth.log and
also displays it in the Server Log of the Connect
Dashboard.
void info(String warnMessage)
Prints the user-specified info message in mirth.log and
also displays it in the Server Log of the Administrator
Dashboard.
void warn(String infoMessage)
Prints the user-specified warning message in mirth.log
and also displays it in the Server Log of the
Administrator Dashboard.
router An instance of com.mirth.connect.server.userutil.VMRouter
available in the entire scope of Connect.

message A String representation of the inbound message. This is only valid in the
JavaScript attachment handler and Pre processor scripts.
message An ImmutableMessage object available in the Postprocessor script,
which provides information about the overall message and all
corresponding connector messages.
connectorMessage An instance of Java object
(com.mirth.connect.userutil.ImmutableConnectorMessage)
representing the message. Refer to the User API Java Classes section
for available methods summary.
msg A JavaScript XML object representation of the inbound message.
Available in Filter and Transformer steps.
tmp A JavaScript XML object representation of the outbound message
template. Available in Filter and Transformer steps only when the
outbound message template has been defined.
channelId A String object containing the channel id. Available only within the
scope of the channel.
connector A String object containing the name of the connector from which it is
referenced.
alerts An instance of Java object
com.mirth.connect.server.userutil.AlertSender. The
sendAlert(String errorMessage)method can be called to raise an
alert.
response An instance of the Java object
(com.mirth.connect.server.userutil.ImmutableResponse)
representing the response received. Refer to the User API Java Classes
section for available methods summary. Only available in the response
transformer.
responseStatus A Status object indicating the response status. Setting this variable will
update the status. Only available in the response transformer.
responseStatusMessage A String representation of the response status message. Setting this
variable will update the status message. Only available in the response
transformer.
responseErrorMessage A Str ing representation of the response error message, if one exists.
Setting this variable will update the error message. Only available in the
response transformer.


## Available Destination Mappings

These variables/templates are always available from the Destination Mappings in all destination connectors.

**Variable Name Description**

${message.channelId} (^) Channel ID The unique ID of the channel that is
processing the message.
${message.channelName} (^) Channel Name The name of the channel that is
processing the message.
${message.messageId} (^) Message ID The sequential ID of the overall message
being processed by the channel.
${message.rawData} (^) Raw Data The message in the inbound protocol of
the connector.
${message.transformedData} (^) Transformed Data The XML representation of the message.
If no filters or transformers are defined
for the connector, this variable will be
empty.
${message.encodedData} (^) Encoded Data The message encoded into the outbound
protocol of the connector, after any
transformations.
${mirth_source} Message Source The source of the message, as defined
in the mirth_source connector map
variable. For HL7 messages, the value
in MSH.4.
${mirth_type} Message Type The type of the message, as defined in
the mirth_type connector map variable.
For HL7 messages, the values in
MSH.9.1 and MSH.9.2, concatenated
together with a hyphen. For example,
ADT-A01.
${mirth_version} Message Version The version of the message, as defined
in the mirth_version connector map
variable. For HL7 messages, the value
in MSH.12.
${DATE} Date The system date and time in the fixed
format: dd- MM- yy_ HH- mm- ss. SSS.
${date.get(format)} Formatted Date The system date and time in the format
specified by the given format string. By
default, the format string pattern is 'yyyy -
M-d H.m.s'. For more information on
date/time formatting patterns, see the
Date/Time Formats section on page 29.
${SYSTIME} Timestamp An integer representation of the system
date and time. The value is the total
number of milliseconds that have passed
since 12:00 a.m. on January 1, 1970.
${UUID} Unique ID A generated universally unique identifier.
${originalFilename} (^) Original File Name The name of the file read by the File
Reader source connector containing the
message being processed. If the
message was not read from a file, this


**Variable Name Description**
value will be the system date/time in
integer format (SYSTIME) with a .dat
extension.
${COUNT} Count A numeric value that is incremented by 1

each time it is referenced within a
particular connector, starting with 1.
Each connector has its own count, so
referencing this variable in one connector
will have no impact on referencing it in
another. The count value for each
connector in a channel is reset each time
that channel is redeployed.
${XmlUtil.encode()} XML Entity Encoder Performs URL encoding on the given

```
string.
```
${XmlUtil.prettyPrint()} (^) XML Pretty Printer Formats an XML document in a
formatted tree structure, with each level
of the tree indented from its parent.
${JsonUtil.prettyPrint()} (^) JSON Pretty Printer Formats a JSON object string
representation such that each
name/value pair of an object appears on
its own line. Additionally, each value in
an array will appear on its own line.
<![CDATA[]]> CDATA Tag An empty CDATA block. Instructs an
XML parser that all data contained within
the block should be interpreted as
character data and not XML markup.
${DICOMMESSAGE} DICOM Message
Raw Data
The message encoded into the DICOM
protocol after any transformations. Used
when writing DICOM data either to a
binary file or over the DICOM protocol.
When used when the outbound data type
is not DICOM, contains the encoded form
of the message.


## Available Source Map Variables

These variables are automatically created by certain source connectors, and sometimes only under certain

conditions. Source map variables are always read-only.

**Variable Connectors Description**

${batchComplete} (^) Any except
DICOM
A Boolean value (true/false) indicating if the
message is the last message in a batch. Only
available when batch processing is enabled.
${batchId} Any except
DICOM
The ID of the batch. This value will always be the
same as the message ID for the first message in
the batch. Only available when batch processing is
enabled.
${batchSequenceId} (^) Any except
DICOM
The sequential ID of the message in a batch,
starting with 1. Only available when batch
processing is enabled.
${contextPath} HTTP Listener The context path of the request.
${destinationSet} (^) Any An array of destination IDs for the destinations
through which the message was/should be sent.
The IDs are the numeric values specified for each
destination on the Destinations tab.
${fileDirectory} (^) File Reader The relative path to the directory from which the file
was read.
${fileLastModified} (^) File Reader An integer representation of the date and time at
which the file was last modified. The value is the
total number of milliseconds that have passed since
12:00 a.m. on January 1, 1970.
${fileSize} File Reader The size, in bytes, of the file that was read.
${headers} HTTP Listener A Java HashMap containing the HTTP headers in
the request.
${localAddress} HTTP Listener,
TCP Listener
The local IP address to which the client has
connected.
${localPort} HTTP Listener,
TCP Listener
The local port to which the client has connected.
${method} HTTP Listener The HTTP method of the request.
${originalFilename} (^) File Reader The name of the file read by the File Reader.
${parameters} HTTP Listener A Java HashMap containing the query parameters
included in the request.
${pollId} File Reader A unique string representing an individual polling event.
All messages generated as a result of the same poll will
have the same poll ID.
${pollSequenceId} (^) File Reader The sequential ID of the message within a poll,
starting with 1.
${pollComplete} File Reader A Boolean value indicating if the message is the
last message in a poll. Only present if the message
is the last message in the poll. Therefore, the value
will always be true.
${protocol} HTTP Listener The protocol and version through which the request
was received. For example, HTTP/1.1.
${query} HTTP Listener The query, with each parameter/value pair delimited
by ampersands, included in the request.


**Variable Connectors Description**

${remoteAddress} (^) HTTP Listener,
TCP Listener
The remote IP address from which the remote client
has connected.
${remotePort} HTTP Listener,
TCP Listener
The remote port from which the remote client has
connected.
${replaced} Any A boolean value indicating if the “Overwrite existing
messages and update statistics” option was
selected when reprocessing the message. This
variable is only available when the message has
been reprocessed.
${reprocessed} Any A boolean value indicating if the message has been
reprocessed. The value will always be true. If the
message was not reprocessed, this variable will not
be available.
${sourceChannelId} (^) Any If the current message is the result of a dispatch
from a Channel Writer destination, this map variable
will be stored. Indicates the ID of the channel the
message was dispatched from.
${sourceMessageId} (^) Any If the current message is the result of a dispatch
from a Channel Writer destination, this map variable
will be stored. Indicates the ID of the message from
the source channel that dispatched this message.
${sourceChannelIds} (^) Any If the current message is the result of a dispatch
from a Channel Writer destination through **two or
more** channels, this map variable will be stored.
Indicates the IDs of the chain of previous channels
the message was dispatched from.
${sourceMessageIds} (^) Any If the current message is the result of a dispatch
from a Channel Writer destination through **two or
more** channels, this map variable will be stored.
Indicates the IDs of the messages from the chain of
previous channels the message was dispatched
from.
${uri} HTTP Listener The URI of the request.
${url} HTTP Listener The URL of the request.


## Available Alert Variables

These variables are available for use in the subject or body of an alert email, or template if the data is

forwarded to a channel.

**Variable Name Description**
${alertId} alertId The unique ID of the alert that was triggered.
${alertName} alertName The name of the alert that was triggered.
${serverId} serverId The ID of the server the alert was triggered on.
${channelId} channelId The ID of the channel in which the alert was
raised.
${channelName} channelName The name of the channel in which the alert was

```
raised.
```
${connectorName} (^) connectorName The name of the connector (e.g. “Source”) in which
the alert was raised, if applicable.
${connectorType} (^) connectorType The type of the connector (e.g. “TCP Sender”) in
which the alert was raised, if applicable.
${error} (^) error The error code, error message and full stack trace
of the exception that caused the alert to be raised.
${errorMessage} errorMessage The error message, without the error code or stack
trace, of the exception that caused the alert to be
raised.
${errorType} errorType The type of error event that caused the alert to
trigger (e.g. “Preprocessor Script”, “Transformer”).
${messageId} messageId The ID of the message being processed when the
alert was triggered.
${systemTime} (^) systemTime An integer representation of the system date and
time. The value is the total number of milliseconds
that have passed since 12:00 a.m. on January 1,
1970.
${date} date The formatted system date and time at which the
alert was raised. This variable is actually a
Velocity DateTool object that allows customization
of the date/time format. For more details, see
[http://velocity.apache.org/tools/devel/javadoc/org/a](http://velocity.apache.org/tools/devel/javadoc/org/a)
pache/velocity/tools/generic/DateTool.html
${globalMapVariable} (^) globalMapVariable Any variable in the global map can be referenced
in alert emails. Simply replace globalMapVariable
with the name of the actual variable.


## User API Java Classes

**Note:** The Javadoc for the entire User API can be viewed from within Connect. Simply right-click in any

JavaScript context and select “View User API” from the context menu.

**Method summary**

### ACKGenerator

com.mirth.connect.server.userutil

- Java utility class for generating ACK response messages.
    static String generateAckResponse(String message, String
       acknowledgementCode, String textMessage)
       Generates a new HL7 ACK message based on the given HL7 message.
       The MSA.1 field is set to the given acknowledgement code, and the
       MSA.3 field is set to the given text message.
       The date/time of message in MSH.7 is set to the current date/time in the
       format yyyyMMddHHmmss.
       No ERR segment is added to the message. To add an ERR segment,
       use the version of this method listed below.
    static String generateAckResponse(String message, boolean isXML, String
       acknowledgementCode, String textMessage, String
       dateFormat, String errorMessage)
       Generates a new HL7 ACK message based on the given HL7 message.
       The MSA.1 field is set to the given acknowledgement code, and the
       MSA.3 field is set to the given text message.
       The date/time of the message in MSH.7 is set to the current date/time
       using the format provided for the dateFormat parameter.
       If the errorMessage parameter is a non-null and non-zero -length string, an
       ERR segment will be added with the given message set to field ERR.1.

### AlertSender

com.mirth.connect.server.userutil

- Java utility class providing the ability to dispatch error events that can trigger an alert.
    Constructor AlertSender(String channelId)
       Instantiates a new AlertSender.
    Constructor AlertSender(ImmutableConnectorMessage connectorMessage)
       Instantiates a new AlertSender.
void sendAlert(String errorMessage)
Dispatches an error event that can trigger an alert.

### Attachment

com.mirth.connect.server.userutil

- Java Class representing the attachment.
- Used to store and retrieve details about message attachments such as the ID, MIME type,
    and content.
       Constructor Attachment()
          Instantiates a new Attachment with no ID, content, or MIME type.
       Constructor Attachment(String id, byte[] content, String type)
          Instantiates a new Attachment with byte data and the given MIME type.
       Constructor Attachment(String id, String content, String type)
          Instantiates a new Attachment with String data using UTF-8 charset
          encoding and the given MIME type.
       Constructor Attachment(String id, String content, String charset,
          String type)
          Instantiates a new Attachment with String data, using the given charset
          encoding and MIME type.


```
String getAttachmentId()
Returns the unique replacement token for the attachment.
byte[] getContent()
Returns the content of the attachment as a byte array.
String getId()
Returns the unique ID for the attachment.
String getType()
Returns the MIME type of the attachment.
void setContent(byte[] data)
Sets the byte content of the attachment.
void setContentString(String content)
Sets the content of the attachment, using UTF-8 encoding.
void setContentString(String content, String charset)
Sets the content of the attachment, using the specified charset encoding.
void setId(String id)
Sets the unique ID for the attachment.
void setType(String type)
Sets the MIME type for the attachment.
```
### Atta chmentUtil

com.mirth.connect.server.userutil.AttachmentUtil

- Provides utility methods for creating, retrieving, and re-attaching message attachments.
static Attachment addAttachment(List<Attachment> attachments, Object
content, String type)
Creates an Attachment and adds it to the provided list.
static Attachment addAttachment(List<Attachment> attachments, Object
content, String type, boolean base64Encode)
Creates an Attachment and adds it to the provided list. If the value of
base64Encode is true, the data will first be Base64-encoded.
static Attachment createAttachment(ImmutableConnectorMessage
connectorMessage, Object content, String type)
Creates an attachment associated with a given connector message, and
inserts it into the database.
static Attachment createAttachment(ImmutableConnectorMessage
connectorMessage, Object content, String type, boolean
base64Encode)
Creates an attachment associated with a given connector message, and
inserts it into the database. If the value of base64Encode is true, the data
will first be Base64-encoded.
static Attachment getMessageAttachment(ImmutableConnectorMessage
connectorMessage, String attachmentId)
Retrieves the attachment with the specified ID for the given connector
message.
static Attachment getMessageAttachment(ImmutableConnectorMessage
connectorMessage, String attachmentId, boolean
base64Decode)
Retrieves the attachment with the specified ID for the given connector
message. If the value of base64Decode is true, the data will first be
Base64-decoded.
static Attachment getMessageAttachment(ImmutableConnectorMessage
connectorMessage, String attachmentId)
Retrieves the attachment with the specified ID for the given connector
message.


static Attachment getMessageAttachment(String channelId, Long messageId,
String attachmentId)
Retrieves the attachment with the given ID from a specific channel
ID/message ID.
static Attachment getMessageAttachment(String channelId, Long messageId,
String attachmentId, boolean base64Decode)
Retrieves the attachment with the given ID from a specific channel
ID/message ID. If the value of base64Decode is true, the data will first be
Base64-decoded.
static
List<String>

```
getMessageAttachmentIds(ImmutableConnectorMessage
connectorMessage)
Returns a List of attachment IDs associated with the given connector
message.
static
List<String>
```
```
getMessageAttachmentIds(String channelId, Long messageId)
Returns a List of attachment IDs associated with the given channel
ID/message ID.
static
List<Attachment>
```
```
getMessageAttachments(ImmutableConnectorMessage
connectorMessage)
Retrieves all attachments associated for the given connector message.
static
List<Attachment>
```
```
getMessageAttachments(ImmutableConnectorMessage
connectorMessage, boolean base64Decode)
Retrieves all attachments associated for the given connector message. If
the value of base64Decode is true, the data will first be Base64-decoded.
static
List<Attachment>
```
```
getMessageAttachments(String channelId, Long messageId)
Retrieves all attachments associated with a specific channel ID/message
ID.
static
List<Attachment>
```
```
getMessageAttachments(String channelId, Long messageId,
boolean base64Decode)
Retrieves all attachments associated with a specific channel ID/message
ID. If the value of base64Decode is true, the data will first be Base64-
decoded.
static
List<Attachment>
```
```
getMessageAttachmentsFromSourceChannel(ImmutableConnector
Message connectorMessage)
Retrieves an attachment from an upstream channel that sent a message
to the current channel.
static
List<Attachment>
```
```
getMessageAttachmentsFromSourceChannel(ImmutableConnector
Message connectorMessage, boolean base64Decode)
Retrieves an attachment from an upstream channel that sent a message
to the current channel. If the value of base64Decode is true, the data will
first be Base64-decoded.
static String reAttachMessage(ImmutableConnectorMessage
connectorMessage)
Replaces any unique attachment tokens for the given connector message
with the corresponding attachment content and returns the full post-
replacement message.
static String reAttachMessage(String raw, ImmutableConnectorMessage
connectorMessage)
Replaces any unique attachment tokens for the given raw message String
with the corresponding attachment content from the given connector
message, and returns the full post-replacement message.
```

```
static byte[] reAttachMessage(String raw, ImmutableConnectorMessage
connectorMessage, String charsetEncoding, boolean binary)
Replaces any unique attachment tokens for the given raw message String
with the corresponding attachment content from the given connector
message and returns the full post-replacement message. If the data is
not binary, uses the given character set encoding. If binary is true, the
raw data is assumed to be Base64-encoded.
static byte[] reAttachMessage(String raw, ImmutableConnectorMessage
connectorMessage, String charsetEncoding, boolean binary,
boolean reattach, boolean localOnly)
Replaces any unique attachment tokens for the given raw message String
with the corresponding attachment content from the given connector
message and returns the full post-replacement message. If the data is
not binary, uses the given character set encoding. If binary is true, the
raw data is assumed to be Base64-encoded. If localOnly is true, only
local attachment tokens will be replaced, and expanded tokens will be
ignored.
```
### AuthenticationResult

com.mirth.connect.plugins.httpauth.userutil

- This class represents the result of an HTTP authentication attempt, used to accept or reject
    requests coming into HTTP-based source connectors.
       void addResponseHeader(String key, String value)
          Adds a new response header to be sent along with the authentication
          response.
static
Authentication
Result

```
Challenged(String authenticateHeader)
Convenience method to create a new AuthenticationResult with the
CHALLENGED status.
static
Authentication
Result
```
```
Failure()
Convenience method to create a new AuthenticationResult with the
FAILURE status.
String getRealm()
Returns the realm that the request has been authenticated with.
Map<String,List
<String>>
```
```
getResponseHeaders()
Returns the map of HTTP headers to be sent along with the
authentication response.
AuthStatus getStatus()
Returns the accept/reject status of the authentication attempt.
String getUsername()
Returns the username that the request has been authenticated with.
void setRealm(String realm)
Sets the realm that the request has been authenticated with.
void setResponseHeaders(Map<String,List<String>>
responseHeaders)
Sets the map of HTTP headers to be sent along with the authentication
response.
void setStatus(AuthStatus status)
Sets the accept/reject status of the authentication attempt.
void setUsername(String username)
Sets the username that the request has been authenticated with.
static
Authentication
Result
```
```
Success()
Convenience method to create a new AuthenticationResult with the
SUCCESS status.
```

```
static
Authentication
Result
```
```
Success(String username, String realm)
Convenience method to create a new AuthenticationResult with the
SUCCESS status.
```
### ChannelUtil

com.mirth.connect.server.userutil

- This utility class allows the user to query information from channels or to perform actions on
    channels.
       static void deployChannel(String channelIdOrName)
          Deploy a channel.
static List<String> getChannelIds()
Get all channel IDs.
static List<String> getChannelNames()
Get all channel names.
static String getChannelName(String channelId)
Get the name for a channel.
static DeployedState getChannelState(String channelIdOrName)
Get the current state of a channel.
static DeployedState getConnectorState(String channelIdOrName, Number
metaDataId)
Get the current state of a connector.
static List<String> getDeployedChannelIds()
Get all deployed channel IDs.
static String getDeployedChannelName(String channelId)
Get the name for a deployed channel.
static List<String> getDeployedChannelNames()
Get all deployed channel names.
       static Long getErrorCount(String channelIdOrName)
          Get the error count statistic for a specific channel.
       static Long getErrorCount(String channelIdOrName, Number
          metaDataId)
          Get the error count statistic for a specific connector.
       static Long getFilteredCount(String channelIdOrName)
          Get the filtered count statistic for a specific channel.
       static Long getFilteredCount(String channelIdOrName, Number
          metaDataId)
          Get the filtered count statistic for a specific connector.
       static Long getQueuedCount(String channelIdOrName)
          Get the queued count statistic for a specific channel.
       static Long getQueuedCount(String channelIdOrName, Number
          metaDataId)
          Get the queued count statistic for a specific connector.
       static Long getReceivedCount(String channelIdOrName)
          Get the received count statistic for a specific channel.
       static Long getReceivedCount(String channelIdOrName, Number
          metaDataId)
          Get the received count statistic for a specific connector.
       static Long getSentCount(String channelIdOrName)
          Get the sent count statistic for a specific channel.
       static Long getSentCount(String channelIdOrName, Number metaDataId)
          Get the sent count statistic for a specific connector.
       static void haltChannel(String channelIdOrName)
          Halt a deployed channel.


```
static boolean isChannelDeployed(String channelIdOrName)
Check if a channel is currently deployed.
static void pauseChannel(String channelIdOrName)
Pause a deployed channel.
static void resetStatistics(String channelIdOrName)
Reset all statistics for a specific channel.
static void resetStatistics(String channelIdOrName, Integer
metaDataId)
Reset all statistics for the specified connector on the given channel.
static void resetStatistics(String channelIdOrName, Integer
metaDataId, Collection<Status> statuses)
Reset the specified statistics for the specified connector on the given
channel.
static void resumeChannel(String channelIdOrName)
Resume a deployed channel.
static void startChannel(String channelIdOrName)
Start a deployed channel.
static void startConnector(String channelIdOrName, Integer
metaDataId)
Start a connector on a given channel.
static void stopChannel(String channelIdOrName)
Stop a deployed channel.
static void stopConnector(String channelIdOrName, Integer
metaDataId)
Stop a connector on a given channel.
static void undeployChannel(String channelIdOrName)
Undeploy a channel.
```
### DatabaseConnection

com.mirth.connect.server.userutil

- Provides the ability to run SQL queries against the database connection object instantiated
    using DatabaseConnectionFactory.
       void close()
          Closes the database connection.
       void commit()
          Makes all changes made since the previous commit/rollback permanent
          and releases any database locks currently held by this
          DatabaseConnection object.
CachedRowSet executeCachedQuery(String expression)
Executes a query on the database and returns a CachedRowSet.
CachedRowSet executeCachedQuery(String expression, List<Object>
parameters)
Executes a prepared query on the database and returns a
CachedRowSet.
int executeUpdate(String expression)
Executes an INSERT/UPDATE on the database and returns the row
count.
int executeUpdate(String expression, List<Object>
parameters)
Executes a prepared INSERT/UPDATE statement on the database and
returns the row count.
CachedRowSet executeUpdateAndGetGeneratedKeys(String expression)
Executes an INSERT/UPDATE statement on the database and returns
a CachedRowSet containing any generated keys.


```
CachedRowSet executeUpdateAndGetGeneratedKeys(String expression,
List<Object> parameters)
Executes a prepared INSERT/UPDATE statement on the database and
returns a CachedRowSet containing any generated keys.
String getAddress()
Returns the server address.
Connection getConnection()
Returns the database connection (java.sql.Connection) this class is
using.
void rollback()
Undoes all changes made in the current transaction and releases any
database locks currently held by this Connection object.
void setAutoCommit(boolean autoCommit)
Sets this connection’s auto-commit mode to the given state.
```
### DatabaseConnectionFactory

com.mirth.connect.server.userutil

- Used to create database connection objects.
    static Connection createConnection(String driver, String address, String
       username, String password)
       Instantiates and returns a new java.sql.Connection object with the given
       connection parameters.
static
DatabaseConnection

```
createDatabaseConnection(String driver, String address)
Instantiates and returns a new DatabaseConnection object with the
given connection parameters.
static
DatabaseConnection
```
```
createDatabaseConnection(String driver, String address,
String username, String password)
Instantiates and returns a new DatabaseConnection object with the
given connection parameters.
static void initializeDriver (String driver)
Initializes the specified JDBC driver.
```
### DateUtil

com.mirth.connect.server.userutil

### - Provides date/time utility methods.

```
String convertDate(String inPattern, String outPattern, String
date)
Parses a date string according to a specified input pattern, and formats
the date back to a string according to a specified output pattern.
String formatDate(String pattern, java.util.Date date)
Formats a java.util.Date object into a string according to a specified
pattern.
String getCurrentDate(String pattern)
Formats the current date into a string according to a specified pattern.
java.util.Date getDate(String pattern, String date)
Parses a date string according to the specified pattern and returns a
java.util.Date object.
```
### DestinationSet

com.mirth.connect.server.userutil

- Utility class used in the preprocessor or source filter/transformer to prevent the message
    from being sent to specific destinations.
       boolean remove(java.util.Collection<java.lang.Object>
          metaDataIdOrConnectorNames)
Stop s the set of destinations specified by
metaDataIdOrConnectorNames from being processed for the
current message.


```
boolean remove(java.lang.Object metaDataIdOrConnectorName)
Stop s the destination specified by metaDataIdOrConnectorName
from being processed for the current message.
boolean removeAll()
Stops all destinations from being processed for the current message.
boolean removeAllExcept(java.util.Collection<java.lang.Object>
metaDataIdOrConnectorNames)
Stop s all of the destinations, except for the set of destinations specified
by metaDataIdOrConnectorNames, from being processed for the
current message.
boolean removeAllExcept(java.lang.Object
metaDataIdOrConnectorName)
Stop s all of the destinations, except for the destination specified by
metaDataIdOrConnectorName, from being processed for the current
message.
```
### DICOMUtil

com.mirth.connect.server.userutil

- Provides DICOM utility methods.
    static String convertDICOM(String imageType,
       ImmutableConnectorMessage connectorMessage)
       Converts merged DICOM data associated with a connector message
       into a specified image format.
    static String convertDICOM(String imageType,
       ImmutableConnectorMessage connectorMessage, boolean
       autoThreshold)
       Converts merged DICOM data associated with a connector message
       into a specified image format.
    static String convertDICOM(String imageType,
       ImmutableConnectorMessage connectorMessage, int
       sliceIndex)
       Converts merged DICOM data associated with a connector message
       into a specified image format.
    static String convertDICOM(String imageType,
       ImmutableConnectorMessage connectorMessage, int
       sliceIndex, boolean autoThreshold)
       Converts merged DICOM data associated with a connector message
       into a specified image format.
    static byte[] getDICOMMessage(ImmutableConnectorMessage
       connectorMessage)
       Re-attaches DICOM attachments with the header data in the connector
       message and returns the resulting merged data as a byte array.
    static byte[] getDICOMRawBytes(ImmutableConnectorMessage
       connectorMessage)
       Re-attaches DICOM attachments with the header data in the connector
       message and returns the resulting merged data as a byte array.
    static String getDICOMRawData(ImmutableConnectorMessage
       connectorMessage)
       Re-attaches DICOM attachments with the header data in the connector
       message and returns the resulting merged data as a Base64-encoded
       string.
static int getSliceCount(ImmutableConnectorMessage
connectorMessage)
Returns the number of slices in the fully-merged DICOM data
associated with a given connector message.


### FileUtil

com.mirth.connect.server.userutil

- Provides file utility methods.
    static byte[] decode(String data)
       Decodes a Base64 string into octets.
static boolean deleteFile(File file)
Deletes a specified File.
    static String encode(byte[] data)
       Encodes binary data into a Base64 string.
static String read(String fileName)
Returns the contents of the file as a string, using the system default
charset encoding.
    static byte[] readBytes(String fileName)
       Returns the contents of the file as a byte array.
    static String rtfToPlainText(String data, String
       replaceLineBreaksWith)
       Converts RTF data to Plain Text with user-specified linebreak. Pass in
       null to use the default \n as the linebreak.
static void write(String filename, boolean append, String data)
Writes a string to a specified file, creating the file if it does not exist.
static void write(String filename, boolean append, byte[] data)
Writes a byte array to a file, creating the file if it does not exist.

### ImmutableConnectorMessage

com.mirth.connect.userutil

- This class represents a connector message and is used to retrieve details such as the
    message ID, metadata ID, status, and various content types.
       String getChannelId()
          Returns the ID of the channel associated with this connector
          message.
Map<String, Object> getChannelMap()
Returns the channel map.
       String getChannelName()
          Returns the name of the channel associated with this connector
          message.
Map<String, Object> getConnectorMap()
Returns the connector map.
       String getConnectorName()
          Returns the name of the connector associated with this connector
          message.
Map<Integer> getDestinationIdMap()
Returns a Map of destination connector names linked to their
corresponding connector metadata ID.
ImmutableMessageContent getEncoded()
Retrieves encoded content associated with this connector message.
       String getEncodedData()
          Retrieves encoded content associated with this connector message.
ImmutableMessageContent getMessageContent(ContentType contentType)
Retrieves content associated with this connector message.
long getMessageId()
Returns the sequential ID of the overall Message associated with
this connector message.
int getMetaDataId()
Returns the metadata ID of this connector message.


ImmutableMessageContent getProcessedRaw()

Retrieves processed raw content associated with this connector
message.
String getProcessedRawData()
Retrieves processed raw content associated with this connector
message.
ImmutableMessageContent getProcessedResponse()

Retrieves processed response content associated with this
connector message.
String getProcessedResponseData()
Retrieves processed response content associated with this
connector message.
String getProcessingError()
Returns the processing error string associated with this connector
message, if it exists.
ImmutableMessageContent getRaw()

Retrieves raw content associated with this connector message.
String getRawData()
Retrieves raw content associated with this connector message.
Calendar getReceivedDate()
Returns the date/time at which the channel created this connector
message.
ImmutableMessageContent getResponse()

Retrieves response content associated with this connector
message.
String getResponseData()
Retrieves response content associated with this connector
message.
Calendar getResponseDate()
Returns the date/time immediately after this connector message's
response is received.
String getResponseError()
Returns the response error string associated with this connector
message, if it exists.
Map<String, Object> getResponseMap()
Returns the response map.
ImmutableMessageContent getResponseTransformed()

```
Retrieves transformed response content associated with this
connector message.
String getResponseTransformedData()
Retrieves transformed response content associated with this
connector message.
int getSendAttempts()
Returns the number of times this message has been attempted to
be dispatched by the connector.
Calendar getSendDate()
Returns the date/time immediately before this connector message's
most recent send attempt.
String getServerId()
Returns the ID of the server associated with this connector
message.
```

```
Map<String, Object> getSourceMap()
Returns the source map.
Status getStatus()
Returns the status (e.g. SENT) of this connector message.
ImmutableMessageContent getTransformed()
Retrieves transformed content associated with this connector
message.
String getTransformedData()
Retrieves transformed content associated with this connector
message.
```
### ImmutableMessage

com.mirth.connect.userutil

- This class represents an overall message and is used to retrieve details such as the
    message ID, specific connector messages, or the merged connector message.
       String getChannelId()
          Returns the ID of the channel associated with this message.
Map<String,
ImmutableConnectorMessage>

```
getConnectorMessages()
Returns a map of connector messages associated with this
message.
Map<String, String> getDestinationIdMap()
Returns a Map of destination connector names linked to their
corresponding connector metadata ID.
ImmutableConnectorMessage getMergedConnectorMessage()
Returns a "merged" connector message containing data from all
connector messages combined.
Long getMessageId()
Returns the sequential ID of this message, as a Long.
String getServerId()
Returns the ID of the server associated with this message.
boolean isProcessed()
Returns whether this message has finished processing through
a channel.
```
### ListBuilder

com.mirth.connect.userutil

- Convenience class to allow fluent building of lists.
    void add(int index, Object element)
       Inserts the specified element at the specified position in this list
       (optional operation).
boolean add(Object e)
Appends the specified element to the end of this list (optional
operation).
boolean addAll(int index, Collection c)
Inserts all of the elements in the specified collection into this list
at the specified position (optional operation).
ListBuilder append(Object e)
Adds an element to the list using the add (java.lang.Object)
method, and returns this builder.
    void clear()
       Removes all of the elements from this list (optional operation).
boolean contains(Object o)
Returns true if this list contains the specified element.
boolean containsAll(Collection c)
Returns true if this list contains all of the elements of the
specified collection.


boolean equals(Object obj)
Indicates whether some other object is "equal to" this one.
Object get(int index)
Returns the element at the specified position in this list.
int hashCode()
Returns a hash code value for the object.
int indexOf(Object o)
Returns the index of the first occurrence of the specified
element in this list, or -1 if this list does not contain the element.
boolean isEmpty()
Returns true if this list contains no elements.
Iterator iterator()
Returns an iterator over the elements in this list in proper
sequence.
int lastIndexOf(Object o)
Returns the index of the last occurrence of the specified element
in this list, or -1 if this list does not contain the element.
ListIterator listIterator()
Returns a list iterator over the elements in this list (in proper
sequence).
ListIterator listIterator(int index)
Returns a list iterator over the elements in this list (in proper
sequence), starting at the specified position in the list.
Object remove(int index)
Removes the element at the specified position in this list
(optional operation).
boolean remove(Object o)
Removes the first occurrence of the specified element from this
list, if it is present (optional operation).
boolean removeAll(Collection c)
Removes from this list all of its elements that are contained in
the specified collection (optional operation).
boolean retainAll(Collection c)
Retains only the elements in this list that are contained in the
specified collection (optional operation).
Object set(int index, Object element)
Replaces the element at the specified position in this list with the
specified element (optional operation).
int size()
Returns the number of elements in this list.
List subList(int fromIndex, int toIndex)
Returns a view of the portion of this list between the specified
fromIndex, inclusive, and toIndex, exclusive.
Object[] toArray()
Returns an array containing all of the elements in this list in
proper sequence (from first to last element).
Object[] toArray(Object[] a)
Returns an array containing all of the elements in this list in
proper sequence (from first to last element); the runtime type of
the returned array is that of the specified array.
String toString()
Returns a string representation of the object.


### Lists

com.mirth.connect.userutil

- Convenience class to allow fluent building of lists.
    Constructor Lists()
static ListBuilder list()
Instantiates a new ListBuilder using an ArrayList.
static ListBuilder list(List list)
Instantiates a new ListBuilder using the given map.
static ListBuilder list(Object e)
Instantiates a new ListBuilder using an ArrayList and the given
element.

### MapBuilder

com.mirth.connect.userutil

- Convenience class to allow fluent building of maps.
    MapBuilder add(Object key, Object value)
       Adds an entry to the map using the put(java.lang.Object,
       java.lang.Object) method, and returns this builder.
void clear()
Removes all of the mappings from this map (optional operation).
boolean containsKey(Object key)
Returns true if this map contains a mapping for the specified
key.
boolean containsValue(Object value)
Returns true if this map maps one or more keys to the specified
value.
Set<?> entrySet()
Returns a Set view of the mappings contained in this map.
boolean equals(Object obj)
Indicates whether some other object is "equal to" this one.
Object get(Object key)
Returns the value to which the specified key is mapped, or null if
this map contains no mapping for the key.
int hashCode()
Returns a hash code value for the object.
boolean isEmpty()
Returns true if this map contains no key-value mappings.
Set<?> keySet()
Returns a Set view of the keys contained in this map.
Object put(Object key, Object value)
Associates the specified value with the specified key in this map
(optional operation).
void putAll(Map m)
Copies all of the mappings from the specified map to this map
(optional operation).
Object remove(Object key)
Removes the mapping for a key from this map if it is present
(optional operation).
int size()
Returns the number of key-value mappings in this map.
String toString()
Returns a string representation of the object.
Collection<?> values()
Returns a Collection view of the values contained in this map.


### Maps

com.mirth.connect.userutil

### - Convenience class to allow fluent building of maps.

```
Constructor Maps()
static MapBuilder map()
Instantiates a new MapBuilder using a HashMap.
static MapBuilder map(Map map)
Instantiates a new MapBuilder using the given map.
static MapBuilder map(Object key, Object value)
Instantiates a new MapBuilder using a HashMap and the given
key/value entry.
```
### MessageHeaders

com.mirth.connect.userutil

- This class represents a collection of header key/value pairs. Used to represent headers in
    an HTTP request or response.
       Constructor MessageHeaders(Map<String>,List<String>> delegate)
          boolean contains(String key)
             Check if headers exist for a given key.
String getHeader(String key)
Get the first header value for the given key.
List<String> getHeaderList(String key)
Get all header values for the given key.
       Set<String> getKeys()
          Get all header keys.

### MessageParameters

com.mirth.connect.userutil

- This class represents a collection of parameters key/value pairs. Used to represent
    parameters in an HTTP request.
       Constructor MessageParameters(Map<String>,List<String>> delegate)
          boolean contains(String key)
             Check if headers exist for a given key.
       Set<String> getKeys()
          Get all header keys.
String getParameter(String key)
Get the first parameter value for the given key.
List<String> getParameterList(String key)
Get all parameter values for the given key.

### Response

com.mirth.connect.userutil

- This class represents a channel or destination response and is used to retrieve details such
    as the response data, message status, and errors.
       Constructor Response()
       Constructor Response(String message)
       Constructor Response(Status status, String message)
       Constructor Response(Status status, String message, String
          statusMessage)
       Constructor Response(Status status, String message, String
          statusMessage, String error)
String getMessage()
Returns the actual response data, as a string.
void setMessage(String message)
Sets the response data.
       enum Status getStatus()
          Returns the Status (e.g. SENT, QUEUED) of this response.


```
void setStatus(Status status)
Sets the status of the Response with one of the following – FILTERED,
TRANSFORMED, SENT, QUEUED, ERROR
String getStatusMessage()
Returns a brief message explaining the reason for the current status.
void setStatusMessage(String statusMessage)
Sets the status message to use for this response.
String getError()
Returns the error string associated with this response, if it exists.
void setError(String error)
```
```
Sets the error string to be associated with this response.
```
### ResponseFactory

com.mirth.connect.server.userutil

- Provides methods to create Response objects.
    static Response getErrorResponse(String message)
       Returns a Response object with ERROR status.
    static Response getSentResponse(String message)
       Returns a Response object with SENT status.
    static Response getFilteredResponse(String message)
       Returns a Response object with FILTERED status.
    static Response getQueuedResponse(String message)
       Returns a Response object with QUEUED status.

### SerializerFactory

com.mirth.connect.server.userutil

- Used to create a serializer for a specific data type for conversion to and from XML.
static Map<String,
Object>

```
getDefaultDeserializationProperties(String dataType)
Returns a map of default properties used to customize how
deserialization from XML to the data type is performed. Valid values for
dataType are “DELIMITED”, “HL7V2”, “NCPDP”.
static Map<String,
Object>
```
```
getDefaultSerializationProperties(String dataType)
Returns a map of default properties used to customize how serialization
from the data type to XML is performed. Valid values for dataType are
“DELIMITED”, “EDI/X12”, “HL7V2”, “HL7V3”, “NCPDP”, “XML”.
static
IXMLSerializer
```
```
getSerializer(String dataType)
Returns a serializer (with toXML and fromXML methods) for a given
data type. Valid values for dataType are “DICOM”, “DELIMITED”,
“EDI/X12”, “HL7V2”, “HL7V3”, “JSON”, “NCPDP”, “RAW”, “XML”.
static
IXMLSerializer
```
```
getSerializer(String dataType, Map<String, Object>
serializationPropertiesMap, Map<String, Object>
deserializationPropertiesMap)
Returns a serializer (with toXML and fromXML methods) for a given
data type. Valid values for dataType are “DICOM”, “DELIMITED”,
“EDI/X12”, “HL7V2”, “HL7V3”, “JSON”, “NCPDP”, “RAW”, “XML”. For a
complete listing of properties that can be put into
serializationPropertiesMap and/or deserializationPropertiesMap, see the
“Serialization and Deserialization Properties” table on page 24.
```

### SMTPConnection

com.mirth.connect.server.userutil

### - Used to send emails.

```
void send(String toList, String ccList, String from, String
subject, String body)
Sends out an email with the system’s default charset.
void send(String toList, String ccList, String from, String
subject, String body, String charset)
Sends out an email with a user-specified charset.
```
### SMTPConnectionFactory

com.mirth.connect.server.userutil

- Used to create an SMTPConnection object.
    static
SMTPConnection

```
createSMTPConnection()
Creates and returns a SMTPConnection object.
```
### VMRouter

com.mirth.connect.server.userutil

### - Used to route messages to another channel within the same instance of Connect.

```
Response routeMessage(String channelName, String message)
Dispatches a message to a channel, specified by the deployed channel
name.
Response routeMessageByChannelId(String channelId, String message)
Dispatches a message to a channel, specified by the deployed channel
ID.
```

Serialization and Deserialization Properties

The properties in the following table are available for the serializationPropertiesMap and/or

deserializationPropertiesMap parameters of SerializerFactory.getSerializer()

### Data Type Property Name Default Value Serialization Deserialization

#### DELIMITED

```
columnDelimiter , ✓ ✓
```
columnNames (^) ✓
columnWidths (^) ✓ ✓
escapeWithDoubleQuote true ✓ ✓
ignoreCR true ✓
numberedRows false ✓
quoteEscapeToken \ ✓ ✓
quoteToken “ ✓ ✓
recordDelimiter \n ✓ ✓
EDI/X12
elementDelimiter * ✓
inferX12Delimiters true ✓
segmentDelimiter ~ ✓
subelementDelimiter : ✓
elementDelimiter * ✓
HL7V2
convertLineBreaks true ✓
handleRepetitions true ✓
handleSubcomponents true ✓
segmentDelimiter \r ✓ ✓
stripNamespaces true ✓
useStrictParser false ✓ ✓
useStrictValidation false ✓ ✓
HL7V3 stripNamespaces true ✓
NCPDP
fieldDelimiter 0x1C ✓ ✓
groupDelimiter 0x1D (^) ✓ ✓
segmentDelimiter 0x1E (^) ✓ ✓
useStrictValidation false ✓
XML stripNamespaces true ✓


## Standard Library Java Classes

**Method Summary**

### ResultSet

### java.sql

### - A set of database result rows containing getter methods.

- for more complete reference, refer to
    [http://docs.oracle.com/javase/7/docs/api/java/sql/ResultSet.html](http://docs.oracle.com/javase/7/docs/api/java/sql/ResultSet.html)
       Blob getBlob(int columnIndex)
          Retrieves the value of the designated column in the current row of this
          ResultSet object as a Blob object in the Java programming language.
       Blob getBlob(String columnName)
          Retrieves the value of the designated column in the current row of this
          ResultSet object as a Blob object in the Java programming language.
boolean getBoolean(int columnIndex)
Retrieves the value of the designated column in the current row of this
ResultSet object as a boolean in the Java programming language.
boolean getBoolean(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as a boolean in the Java programming language.
       byte getByte(int columnIndex)
          Retrieves the value of the designated column in the current row of this
          ResultSet object as a byte in the Java programming language.
       byte getByte(String columnName)
          Retrieves the value of the designated column in the current row of this
          ResultSet object as a byte in the Java programming language.
       Date getDate(int columnIndex)
          Retrieves the value of the designated column in the current row of this
          ResultSet object as a java.sql.Date object in the Java programming
          language.
       Date getDate(String columnName)
          Retrieves the value of the designated column in the current row of this
          ResultSet object as a java.sql.Date object in the Java programming
          language.
double getDouble(int columnIndex)
Retrieves the value of the designated column in the current row of this
ResultSet object as a double in the Java programming language.
double getDouble(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as a double in the Java programming language.
float getFloat(int columnIndex)
Retrieves the value of the designated column in the current row of this
ResultSet object as a float in the Java programming language.
float getFloat(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as a float in the Java programming language.
int getInt(int columnIndex)
Retrieves the value of the designated column in the current row of this
ResultSet object as an int in the Java programming language.
int getInt(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as an int in the Java programming language.
       long getLong(int columnIndex)


```
Retrieves the value of the designated column in the current row of this
ResultSet object as a long in the Java programming language.
long getLong(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as a long in the Java programming language.
Object getObject(int columnIndex)
Retrieves the value of the designated column in the current row of this
ResultSet object as an O bject in the Java programming language.
Object getObject(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as an Object in the Java programming language.
String getString(int columnIndex)
Retrieves the value of the designated column in the current row of this
ResultSet object as a String in the Java programming language.
String getString(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as a String in the Java programming language.
Time getTime(int columnIndex)
Retrieves the value of the designated column in the current row of this
ResultSet object as a java.sql.Time object in the Java programming
language.
Time getTime(String columnName)
Retrieves the value of the designated column in the current row of this
ResultSet object as a java.sql.Time object in the Java programming
language.
boolean next()
Moves the cursor down one row from its current position.
```
### CachedRowSet

### javax.sql.rowset

### - Subclass of ResultSet. Most commonly used methods are inherited from ResultSet.

- for more complete reference, refer to
    [http://docs.oracle.com/javase/7/docs/api/javax/sql/rowset/CachedRowSet.html](http://docs.oracle.com/javase/7/docs/api/javax/sql/rowset/CachedRowSet.html)
       int size()
          Returns the number of rows in this CachedRowSet object.


## JavaScript E4X Classes

### XML

- For more complete reference, refer to [http://www.devx.com/webdev/Article/33393/0/page/3](http://www.devx.com/webdev/Article/33393/0/page/3)
appendChild(childToAppend)
Appends a new child node to the XML object.
attribute(attributeName)
Returns the value of the attribute with the given name.
childIndex()
Returns the zero-based index of the node within its parent.
children()
Returns an XMLList containing the all the children objects of the current node.
copy()
Returns a deep copy of the XML object.
insertChildAfter(childToInsertAfter, childToInsert)
Inserts a new child node after the specified child in the XML object.
insertChildBefore(childToInsertBefore, childToInsert)
Inserts a new child node before the specified child in the XML object.
length()
Returns the length of the XML. That is, the number of child nodes.
name()
Returns the name of the node.
setName(name)
Sets the name to the node.

### XMLList

- For more complete reference, refer to [http://www.devx.com/webdev/Article/33393/0/page/3](http://www.devx.com/webdev/Article/33393/0/page/3)
length()
Returns the length of the XMLList. That is, the number of objects in the list.
children()
Returns an XMLList containing the all the children objects of the current node.
copy()
Returns a deep copy of the XMLList object.

For more details and complete reference, refer to:

[http://www.devx.com/webdev/Article/33393](http://www.devx.com/webdev/Article/33393)

[http://wso2.com/project/mashup/0.2/docs/e4xquickstart.html](http://wso2.com/project/mashup/0.2/docs/e4xquickstart.html)


## Built-in Code Template JavaScript Functions

**Function summary**

### Message Functions

```
JavaScript XML createSegment('segmentName')
Creates a new segment that can be used in any message.
JavaScript XML createSegment('segmentName', msg)
Creates a new segment in specified message (msg or tmp).
JavaScript XML createSegment('segmentName', msg, i)
Creates a new segment in specified message (msg or tmp) at segment
index i.
JavaScript XML createSegmentAfter('insertSegmentName', afterThisSegment)
Creates a new segment and inserts it after the target segment.
void delete msg['segment'][index]
Deletes a segment from the message. The index is optional, and is only
necessary when deleting a single segment from a list of repeating
segments.
```
### Utility Functions

```
Attachment addAttachment(data, type, base64Encode)
Adds attachment (String or byte[]) to message, using given MIME type. If
base64Encode is true, the given content will be Base64-encoded. If
base64Encode is false or missing, the content will be stored without
encoding.
Attachment getAttachment(String attachmentId, boolean base64Decode)
Returns a specific attachment with a given ID with this message or null if
not found. If base64Decode is true, the content of the attachment will first
be Base64-decoded.
Attachment getAttachment(String channelId, Long messageId, String
attachmentId, boolean base64Decode)
Returns a specific attachment associated with a given ID with any
channel/message, or null if not found. If base64Decode is true, the
content of the attachment will first be Base64-decoded.
List<Attachment> getAttachmentsId()
Returns a list of attachment IDs of the channel/message.
List<Attachment> getAttachmentsIds(String channelId, Long messageId)
Returns a list of all attachment IDs of any channel/message.
List<Attachment> getAttachments(boolean base64Decode)
Returns a list of attachments of the message. If base64Decode is true, the
content of each attachment will be Base64-decoded.
Attachment updateAttachment(Attachment attachment, boolean
base64encode)
Updates an attachment associated with the current connector message. If
base64Decode is true, the content will first be Base64 encoded.
Attachment updateAttachment(String attachmentId, String/byte[] data,
String type, boolean base64encode)
Updates an attachment associated with the current message. Type is
mime type. If base64Decode is true, the content will first be Base64-
encoded.
```

## Date/Time Formats

**Letter Date/Time Component Examples**

G (^) Era designator AD
y (^) Year 1996 ; 96
M (^) Month in year July; Jul; 07
w (^) Week in year 27
W (^) Week in month 2
D (^) Day in year 189
d (^) Day in month 10
F (^) Day of week in month 2
E (^) Day in week Tuesday; Tue
a (^) Am/pm marker PM
H (^) Hour in day (0-23) 0
k (^) Hour in day (1-24) 24
K (^) Hour in am/pm (0-11) 0
h (^) Hour in am/pm (1-12) 12
m (^) Minute in hour 30
s (^) Second in minute 55
S (^) Millisecond 978
z (^) Time zone Pacific Standard Time; PST; GMT- 08:00
Z (^) Time zone -0800
Date/Time Format Examples
**Date/Time Pattern Result**

### "yyyy.MM.dd G 'at' HH:mm:ss z" 2001.07.04 AD at 12:08:56 PDT

### "EEE, MMM d, ''yy" Wed, Jul 4, '01

### "h:mm a" 12:08 PM

### "hh 'o''clock' a, zzzz" 12 o'clock PM, Pacific Daylight Time

### "K:mm a, z" 0:08 PM, PDT

### "yyyyy.MMMMM.dd GGG hh:mm aaa" 02001.July.04 AD 12:08 PM

### "EEE, d MMM yyyy HH:mm:ss Z" Wed, 4 Jul 2001 12:08:56 - 0700

### "yyMMddHHmmssZ" 010704120856- 0700


## Common MIME Types

text/plain Plain Text
text/html HTML
text/xml XML
application/pdf Adobe Portable Document Format (PDF)
application/rtf Rich Text Format
application/dicom DICOM
application/EDI-X12 EDI X12 Data
application/EDI-EDIFACT EDI EDIFACT Data
application/zip ZIP Archive File
image/jpg JPEG Image
image/jpeg JPEG Image
image/gif GIF Image
image/png Portable Network Graphics (PNG) Image


## Common Email Headers

bcc Blind Carbon Copy. A list of secondary recipient email addresses that should
not be disclosed to other recipients.
cc Carbon Copy. A list of secondary recipient email addresses.
Expiry-Date The date/time at which a message is no longer valid.
From The “from” address for the message.
Importance The importance of the message, such as “High” or “Low”. Different email
clients will indicate the importance of the message in different manners.
Keywords Key words for the email message. Used by some email clients to categorize
the email.
Reply-To The suggested email address to which replies to the email should be sent.
Return-Receipt-To The email address to which a requested delivery notification should be sent.
Subject The subject of the email.
To A list of primary recipient email addresses.
X-Mailer Email client used to send the message.
