```
nextgen.com
```
Mirth

```
®
Connect
```
Fundamentals Training

Presentation Slides

Document Version 4. 1
July 2025

© 2009 - 2025 NextGen Healthcare, Inc.



```
i nextgen.com
```
**Legal Notice**

Mirth Connect Fundamentals Training Presentation Slides, document version 4.

Copyright © 2022 NextGen Healthcare, Inc. All rights reserved.

This book is provided as part of the Mirth Connect Fundamentals Training or Mirth Connect
Fundamentals Certification Training class for the sole purpose of the attendee’s personal training use.

It is not available for sale or resale apart from attending one of the aforementioned training classes
hosted by NextGen Healthcare, Inc.

This document may not to be distributed, reproduced, transmitted, published or modified in any manor
without the express written permission of NextGen Healthcare, Inc.

All names, logos, images and marks appearing within these materials, except as otherwise noted, are

trademarks owned or used under license by NextGen Healthcare, Inc. The use or misuse of these
trademarks or any other content is prohibited.

The information in this book is to be used for training purposes only. Neither NextGen Healthcare, Inc.
nor the author of this book assume any responsibility for any errors or omissions, or for damages

resulting from the use of the information contained herein.

© 2009 - 2025 NextGen Healthcare, Inc
.



## iii nextgen.com

**Contents**

© 2009 - 2025 NextGen Healthcare, Inc


© 2009 - 2025 NextGen Healthcare, Inc


© 2009 - 2025 NextGen Healthcare, Inc


© 2009 - 2025 NextGen Healthcare, Inc


© 2009 - 2025 NextGen Healthcare, Inc

- Course Introduction In-Class Presentation
   - Introductions
   - Course Objectives
   - Course Prerequisites and Assumptions
   - Course Materials
- Introduction to Mirth Connect
   - History of MirthConnect
   - What is Mirth Connect?
   - Sample Use Cases
- Getting Started
   - Installation
   - Starting/Stopping the Mirth Connect Server
   - Mirth Connect Server Manager
   - Lab 1: Start/Stop Mirth Connect Server
   - Mirth Connect Administrator
   - Launching the Administrator
   - Lab 2: Launch Mirth Connect Administrator
- Key Concepts
   - Channels
   - Connectors
   - Creating Channels
   - Channel Summary
   - Channel Properties
   - Message Storage
   - Deploying Channels
   - Stopping /Starting Channels
   - Destination Mappings
   - Lab 3: Create and Deploy a Simple Channel
   - Velocity Template Variables
   - Message Statistics
   - Viewing Processed Messages
   - Reprocessing Messages iv nextgen.com
   - Removing Messages
   - Send Message Tool
   - Web Administrator
   - Web Dashboard
- Message Processing
   - Message Flow in a Channel
   - Message Transformation
   - Message States
   - Data Types and Properties
- Filters
   - Filters
   - Inbound Message Template
   - Rule Builder Filters
   - Lab 4: Create Filters Using Rule Builder
- Transformers
   - Mapper Transformers
   - Lab 5: Create Text Report Using Mapper Transformer Steps
   - Outbound Message Template
   - Message Builder Transformers
   - Lab 6: Create XML Message Using Message Builder Transformer Steps
   - Message Modification
   - Lab 7: Message Modification Using Message Builder Transformer Steps
- Automatic Mapper Variables
   - Source Map Variables
   - Mirth Variables
   - Response Map Variables
- Custom Metadata
- Introduction to E4X
- Channel Organization
   - Channel Groups
   - Lab 8: Create and Populate a Channel Group
   - Channel Tags
- Connectors
   - Source Connectors v nextgen.com
   - Source Responses
   - TCP Socket Listeners
   - TCP Connectors
   - Lab 9: Receive, Send Message Using TCP Connectors in MLLP Mode
   - Polling Readers
   - File Connectors
   - Lab 10: Create a Channel with File Connectors
   - Database Connectors
   - Lab 11: Generate HL7 Messages from Rows in a Database Table
   - Lab 12: Extract Data from Inbound HL7 Messages, Write Data to Database
   - Document Writer Connector
   - Lab 13: Generate a Patient Report PDF Document Using Document Writer
   - SMTP Sender Connector
- Configuration Map
   - Configuration Map
   - Lab 13: Create and Use Configuration Map Variables
- Iteration
   - Iteration in Mirth Connect
   - Iterator Transformer
   - Lab 14: Use Iterator Transformer to Build Message with Repeating Data
   - Iterator Filter
   - Lab 15: Use Iterator Filter for Data in Repeating Segment
- Using JavaScript in Mirth Connect
   - JavaScript Basics
   - JavaScript & E4X in Mirth Connect
   - Iterating Over Message Segments
   - JavaScript Transformers
   - Mapper Variables in JavaScript
   - Lab 17: Use a JavaScript Transformer to Iterate Over Segments and Create a Lab Report
   - Adding Segments to a Message
   - Deleting Segments from a Message
   - Lab 18: Use a JavaScript Transformer to Add, Delete Segments
   - JavaScript Filters
   - Code Templates vi nextgen.com
   - Global & Channel Scripts
   - Deploy Scripts
   - Global Map & Global Channel Map
   - Undeploy Scripts
   - Preprocessor Scripts
   - Postprocessor Scripts
- Responses
   - Responses
   - Auto-Generated ACKs
   - Response Validation
   - Response Transformers
   - HL7 Queries
   - Lab 19: Modify a destination’s response using a Response Transformer
- Mapper Variable Review
- Internal Routing
   - Internal Routing
   - Channel Connectors
   - Lab 20: Route Messages Using Channel Connectors
- Batch Processing
   - Batch Processing
   - Lab 21: Process XML Batch File
- Channel Configuration
   - Destination Queues & Retries
   - Destination Chains
   - Deploy/Start Dependencies
- Connect Operations & Administration
   - Logs and Logging
   - User Management
   - Events
   - Settings
   - Alerts
   - Extensions
   - Import/Export
   - Server Configuration Backup vii nextgen.com
   - Data Pruning
   - Backend Database
   - Command Line Interface (CLI)
   - Lab 22: Launch the CLI
- Supplemental: Introduction to Message Standards S- Supplemental Message Standards Presentation
   - Message Standards S-
   - What is HL7? S-
   - HL7 Version 2.x S-
   - Lower Layer Protocol (LLP) S-
   - HL7 Version 2.x in Connect S-
   - Lab: Manually Parse an HL7 Message S-
   - XML S-
   - XML Namespaces S-
   - HL7 Version 3 S-
   - EDI/X12 S-
   - X12 S-
   - EDI (EDIFACT) S-
   - NCPDP S-
   - DICOM S-
   - Delimited Text S-
   - Raw Data S-



**NOTES**

Mirth

```
®
Connect by NextGen Healthcare
```
Fundamentals Training

```
Document Version 4.
November 2022
```
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute.
```
(^)


**NOTES**

# Course Introduction

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^2)
(^)


**NOTES**

### Introductions

- About your instructor
- About yourselves
    - Name
    - Organization
    - Position/job
    - How do you/will you use Mirth Connect?
    - Experience with Mirth Connect
    - Expectations

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^3)
(^)


**NOTES**

### Course Objectives

- In this course, you will...
    - Configure and start the Mirth Connect Server and Mirth Connect Administrator
    - Create and deploy a wide variety of channels
    - Understand the processing flow of message data through a channel
    - Process and view message data
    - Use filters to accept/reject messages based on content
    - Use transformers to extract, manipulate message data
    - Learn about E4X, and its relationship to message data
    - Configure several different connector types
    - Use iteration to process repeating data in messages

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^4)
(^)


**NOTES**

### Course Objectives

- In this course, you will...
    - Use JavaScript to implement complex channels, transformers and filters
    - Process responses received from a destination and generate custom responses
    - Internally route messages between channels
    - Process message batches
    - Configure alerts
    - Use the Command Line Interface (CLI)
    - Manage and maintain Mirth Connect operations and configuration settings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^5)
(^)


**NOTES**

### Course Prerequisites and Assumptions

- Familiarity with the following concepts and technologies is helpful:
    - Health information technologies, EMRs, etc.
    - Programming languages (JavaScript, Java)
    - Messaging standards (HL7, EDI, X12, etc.)
    - Databases, SQL, JDBC
    - XML
    - Communication protocols (TCP, MLLP, FTP, SOAP)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^6)
(^)


**NOTES**

### Course Materials

- Course presentation
    - Copies of all presentation slides
- Mirth Connect FundamentalsTraining Lab Book
- Mirth Connect Programming Reference
- Student Information PDF

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^7)
(^)

- Dedicated virtual workspace (Labs/Final exam)


**NOTES**

### Lab Resources

- Folde r with lab resources (C: \)
    - Completed lab channels
    - Other sample channels
    - Sample messages
    - Scripts and other files used in labs
    - Setup files for applications used in labs

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^8)
(^)


```
©20 15 - 2022 NextGen Healthcare, Inc. 9 / 10 nextgen.com
```
**NOTES**

## Introduction to Mirth Connect

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^9)
(^)


**NOTES**

### What is Mirth Connect?

- Multi-standard, cross-platform integration engine
- Facilitates message exchange, filtering, transformation, extraction, and routing
- Mirth Connect Administrator used to develop and manage message interfaces
    (channels)
- Channels are deployed to Mirth Connect Server where the necessary transport
    connectors are created
- Supports a variety of connectors (TCP, HTTP, File, JDBC, Web Services, etc.)
- Open-source project
    - Released under Mozilla Public License 1.
    - Enterprise extensions also available

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^11)
(^)


**NOTES**

### Sample Use Cases

```
1.
2.
```
```
Lab information system sends HL7 message to Mirth Connect over MLLP
After extracting required patient data from the message, Mirth Connect then:
...inserts patient data into EHR database
...creates PDF document with extracted patient demographic data
...uploads the PDF to secure FTP server
```
```
SQL INSERT
```
Mirth Connect

```
TCP/MLLP PDF^ Document^
```
```
Secure FTP
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^12)
(^)


**NOTES**

### Sample Use Cases

```
1.
2.
```
```
Mirth Connect reads patient data from hospital’s EMR system
Using mapped data elements, Mirth Connect generates an HL7 message and sends it to a clinic for outpatient care
```
Mirth Connect

```
SQL SELECT TCP/MLLP
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^13)
(^)


**NOTES**

# Getting Started

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^14)
(^)


**NOTES**

### Installation

- Installer available for Windows, Linux, and macOS
- Requires prior installation of a Java Runtime Environment (JRE)
    - Mirth Connect versions 3.7 or later support:
       - All versions of Java 8 or above
       - Oracle’s commercial distribution of Java
       - OpenJDK and other open-source distributions

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^15)
(^)


**NOTES**

### Installation

- Setup wizard for specifying installation options:
    - Installation folder
    - Mirth Connect components to install
    - Start menu folder, shortcut options
    - Ports used by Mirth Connect
    - Password requirements
    - Folders for application data and logs
    - Install the Mirth Connect Server as a service

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^16)
(^)


**NOTES**

### Installation

- Destination directory for installation
    - Default installation directory for Windows:
       - C:\Program Files\Mirth Connect
    - Default installation directory for Linux/Mac:
       - /Applications/Mirth Connect

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^17)
(^)


**NOTES**

### Installation

- Mirth Connect components to install:
    - Mirth Connect Server (required)
    - Mirth Connect Server Manager
    - Mirth Connect Command Line Interface (CLI)
    - Mirth Connect Administrator Launcher
       - Launches a separate setup wizard once Mirth Connect
          setup has completed
- Standalone setup executables available for CLI
    and Administrator Launcher

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^18)
(^)


**NOTES**

### Installation

- Network ports used by Mirth Connect
    - Web Start Port (HTTP Port)
    - Administrator Port (HTTPS Port)
- Specified ports cannot be in use by other
    applications on server

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^19)
(^)


**NOTES**

### Installation

- Password requirements for Mirth Connect users
    - Value of 0 means requirement not in effect

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^20)
(^)


**NOTES**

### Installation

- Locations for application data, log folders
    - By default, created under specified installation folder
- Data stored in appdata folder:
    - Backend database files (Derby)
    - Configuration Map properties
    - Extension properties
    - KeyStore file
    - Temporary files
- Logs folder contains Mirth Connect’s log files

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^21)
(^)


**NOTES**

### Installation

- Option to install Mirth Connect as a service
    - When running as a service, the Mirth Connect Server
       will start & stop with the operating system

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^22)
(^)


**NOTES**

### Installation

- Prior to upgrading an existing installation of Mirth Connect, review online
    Upgrade Guide for important information
       - Available on Mirth Connect GitHub site:

```
https://github.com/nextgenhealthcare/connect/wiki/Upgrading
```
- Upgrade guide includes:
    - Manual steps that may be required as part of upgrade
       - For example, backup/restore of configuration file customizations
       - Updating of any installed Enterprise Extensions or custom plugins
    - Version-specific upgrade information
       - How new features or feature changes can affect your existing configuration/channels

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^23)
(^)


**NOTES**

### Starting the Mirth Connect Server

- Windows:
    - Mirth Connect Server Manager
    - Windows Services console
    - mcservice.exe executable
- Linux
    - Mirth Connect Server Manager
       - Depends on distribution used
    - mcservice script
- macOS
    - mcservice script
       - Restarting the Mirth Connect Server
          is required whenever changes are
          made to Mirth Connect’s configuration
       - Examples:
          - User password requirements updated
          - New Enterprise Extension(s) installed
          - Backend database changed to a different
             database server
          - Any configuration change in
             mirth.properties

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^24)
(^)


**NOTES**

### Mirth Connect Server Manager

- Notification tray applet
- Perform basic management and
    configuration of local Mirth Connect
    Server
- Launch Administrator
- Divided into four tabs:
    - Service
    - Server
    - Database
    - Info

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^25)
Mirth Connect Server Manager
in Notification Tray


**NOTES**

### Mirth Connect Server Manager

- Service tab
    - Start/Stop/Restart local Server
       - Not supported on Mac and some Linux
          distributions
    - Buttons reflect current state of the service
       - Click Refresh to update

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^26)
(^)


**NOTES**

### Mirth Connect Server Manager

- Server tab
    - _HTTP Port_
       - Used to access Web Administrator page
          using HTTP
       - Default value: 8080
    - _HTTPS Port_
       - Used by the Administrator & CLI to
          communicate with the Connect Server
       - Can also be used to access Web
          Administrator page using HTTPS
       - Default value: 8443
          - _Server Memory (mb)_
             - Max JVM heap size
- Logging Levels
- View Log Files

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^27)
(^)


**NOTES**

### Mirth Connect Server Manager

- Database tab
    - Change Mirth Connect’s back-end database

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^28)
(^)


**NOTES**

### Mirth Connect Server Manager

- Info tab
    - Server Version
    - Server ID
    - Java Version

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^29)
(^)


**NOTES**

### Starting the Mirth Connect Server

- **LAB 1:** Start/Stop Mirth Connect Server
    - Stop server using Server Manager
    - Start/stop server using command-line executable
       - Start with “mcservice /start”
       - Stop with “mcservice /stop”
       - Check status with “mcservice /status”
    - Start server from Windows Services Console

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^30)
(^)


**NOTES**

### Lab 2: Launch Mirth Connect Administrator

- Tool used for all channel development and management
- Can be run from anywhere in relation to the Mirth Connect Server
    - For example:
       - Administrator and Server on same computer (localhost)
       - Administrator and Server on different computers, same LAN
       - Administrator and Server on different networks
    - Web access required

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^31)
(^)


**NOTES**

### Mirth Connect Administrator

- Administrator communicates with Server securely over HTTPS
    - Uses configured HTTPS port (8443 by default)

```
HTTPS HTTPS
```
```
https://serveraddress:8443
```
```
Administrator Server
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^32)
(^)


**NOTES**

### Launching the Administrator

- Administrator Launcher
    - Standalone application for launching the
       Administrator
    - Does not require installation of JRE on
       client computer
          - JRE 8 built-in
    - Manage multiple Mirth Connect Server
       connections
    - Compatible with all Mirth Connect
       versions back to 2.x

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^33)
(^)


**NOTES**

### Launching the Administrator

- Administrator Launcher can also be opened from:
    - Mirth Connect Server Manager
    - Web Administrator page
- Installer associates Java Network Launch
    Protocol (.jnlp) files with the Launcher
- If Administrator Launcher is not installed,
    .jnlp files are opened with Java Web Start
       - Requires installation of Java
       - Java Web Start no longer supported in Java 11

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^34)


**NOTES**

### Launching the Administrator

- Logging in
    - Address of the Mirth Connect Server
       - Populated automatically
    - Username
       - Default: admin
    - Password
       - Default: admin

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^35)
(^)


**NOTES**

### Launching the Administrator

- Must provide required user
    information when logging in for
    the first time
       - Initially, only admin user exists
          (password: admin)
       - Any additional users will also see
          Welcome dialog upon first login

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^36)
(^)


**NOTES**

### Launching the Administrator

- Notifications
    - Displayed upon successful login
    - Important news, notes, release
       information regarding Mirth Connect
    - Ability to disable notifications on
       login

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^37)
(^)


**NOTES**

### Launching the Administrator

- **LAB 2:** Launch Mirth Connect Administrator using the Administrator Launcher
    - Open the Administrator Launcher
    - Create a new connection (or use existing one)
    - Log in with admin/admin
    - Overwrite default admin user with your information (or keep as admin/admin)
       - Don’t forget your username/password

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^38)
(^)


**NOTES**

### Mirth Connect Administrator

- Client application used for all
    channel development and
    management
- Window comprised of menu,
    view panes
- Different views for different tasks
    - Dashboard, Channel, Edit Channel,
       Settings, etc.
- Available menu tasks change
    depending upon selected view
- **Demo:** Brief walkthrough of
    Administrator

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^39)
(^)


**NOTES**

# Key Concepts

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^40)
(^)


**NOTES**

### Channels

- A channel defines an interface to exchange data between a message provider
    and one or more destination systems
       - No defined limit to the number of channels
- Source connector connects to a data source and either listens or polls for data
- Destination connectors route transformed messages to destination systems

stination (^) Destination
nnector
Source
Connecto
Source stination^ Destination
nnector
stination (^) Destination
nnector
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^41)
Channel
De
Co
De
r Co
De
Co


**NOTES**

### Connectors

- Allow channels to communicate with systems external to Mirth Connect
- One source connector, one or more destination connectors
    - No defined limit to the number of destination connectors
- Several supported standard protocols
    - TCP/MLLP, JDBC, File, FTP, PDF, RTF, SMTP, HTTP, web services, etc.
- Each connector has properties which can be configured through the
    Administrator
       - IP address, port, polling frequency, timeout, etc.

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^42)
(^)


**NOTES**

### Creating Channels

- Select _New Channel_ in Channels view
- Define basic channel properties on Summary tab
- Select source connector and define properties on Source tab
- Select destination connector(s) and define properties on Destination tab
- Define any scripts on Scripts tab

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^43)
New Channel
Edit Channel
Tabs


**NOTES**

### Channel Summary

- Defines channel’s common
    properties
       - Channel Properties
          - Name, data types, dependencies,
             initial state, enabled state, etc.
       - Message Storage
       - Message Pruning
       - Channel Tags
       - Custom Metadata
       - Optional description

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^44)
(^)


**NOTES**

### Channel Properties

- Channel Properties
    - Name
       - Max 40 characters – alphanumeric/space/hyphen/underscore
    - Inbound/outbound data types and properties
    - Specify dependencies
    - Initial state upon deployment
       - Started, Stopped or Paused
    - Attachment handling (advanced)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^45)


**NOTES**

### Channel Properties

- Channel Properties
    - Enabled/disabled
       - Only enabled channels can be deployed
       - Channel automatically disabled when saving with errors (e.g., missing required property)
    - Clear Global Channel Map on deploy
    - Channel ID
       - Unique number (GUID) generated upon creation
       - Can be selected, copied

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^46)


**NOTES**

### Channel Properties

- Channel Properties
    - Revision number
       - Incremented each time channel is saved
       - **Note:** Changing channel metadata such as Enabled/Disabled, Pruning settings, etc. does not
          update the revision number
    - Last modified date/time
    - Channel tags

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^47)


**NOTES**

### Message Storage

- By default, data for processed messages is
    stored in Mirth Connect’s backend database
       - As a message is processed through a channel,
          data about the message is persisted in a way
          that allows the message to resume processing
          where it left off in the case of a system failure
          or channel halt
             - Durable Message Delivery
       - Also allows message data to be viewed, reprocessed
       - Durable Message Delivery and viewing/reprocessing depend upon selected storage option

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^48)


**NOTES**

### Message Storage

- Five message storage levels:
    - Development
    - Production
    - Raw
       - Metadata
       - Disabled
- Each level determines:
    - What message information is stored
    - Availability of Durable Message Delivery
    - Performance
- Development, Production, Raw have options to:
    - Encrypt message content
    - Remove content on completion (all messages or only filtered)
    - Remove attachments on completion

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^49)


**NOTES**

### Message Storage

- Message content vs. message metadata
    - Message content
       - The actual message data in various states as it passes through the channel, variable maps, errors,
          attachments
    - Message metadata
       - Metadata about the message, such as message ID, server ID, status, received date/time, etc.
- **Note:** Error data will always be stored unless message storage is disabled

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^50)
(^)


**NOTES**

### Deploying Channels

- A channel must be **deployed** before it can be used
    - That is, before it can actively process message data
- Only enabled channels can be deployed
- Deploy from Channels view or Edit Channel view
    - _Deploy Channel_ menu item in either view
- Channels can also be un-deployed
    - _Undeploy Channel_ menu item in Dashboard view
- Implicit deployment upon server startup
    - All enabled channels will be deployed
- Implicit un-deployment upon server shutdown

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^51)
(^)


**NOTES**

### Deploying Channels

```
Saved Channels
Listed in Channels view
```
```
Deployed Channels
Listed in Dashboard view
```
- Channels can be edited after deployment
    - However, channel must then be redeployed for changes to take effect

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^52)
Channel C
Channel B Channel B
Channel A Channel A


**NOTES**

### Deploying Channels

- Dashboard and Channels views display deployment data for each channel:
    - Date/time of last deployment
       - Highlighted for two minutes after deployment
    - Revision delta (Rev Δ)
       - The number of times changes to the channel have been saved since it was last deployed
       - Highlighted while non-zero

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^53)


**NOTES**

### Stopping/Starting Channels

- Deployed channels (and groups of channels) can be stopped, started or
    paused from the Dashboard
- The default status of a channel is started
    - Configurable on channel’s Summary tab
- When a channel is stopped, the source connector will not receive new
    messages (reject connections)
- _Stop Channel_ stops the channel “safely”
    - Allows the current message to finish processing
    - While the channel is stopping, option to _Halt Channel_
       - “Kills” the channel
       - Use for non-responsive channel (e.g., code in an infinite loop)
       - Does not remove the message being processed when the channel is halted

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^54)
(^)


**NOTES**

### Starting/Stopping Channels

- _Pause Channel_ stops the source connector, but leaves all destinations running
    - Allows queued messages to continue processing without accepting new messages
- Individual destinations can be stopped
    - Only if queuing is enabled for that destination
    - Will still process through destination’s filter, transformer
    - Messages will be queued for that destination

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^55)
(^)


**NOTES**

### Destination Mappings

- Every destination connector has a _Destination Mappings_ list
    - Populated with values that can be used in connector properties
    - Values can be added to this list
- Values can be used in any text fields
    - Populated via drag-and-drop
       - Inserts reference using syntax: ${objectName}

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^56)


**NOTES**

### Channels

- **LAB 3:** Create and deploy a simple “pass-through” channel
    - TCP Listener source connector
       - MLLP transmission mode
    - File Writer destination connector
       - Write received message to file
    - Save and deploy channel
    - Send a test message using HL7 Inspector
       - Third party tool for sending over MLLP protocol
_(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^57)
(^)


**NOTES**

### Channels

- **LAB 3** (continued)
    - View results:
       - Correct statistics in Administrator Dashboard
       - HL7 Inspector receives ACK message from channel
       - File written to outbox folder

```
/Training/outbox
```
```
HL7 MLLP^6661
Inspector
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^58)
Channel
TC
P Listener
File Write
r


**NOTES**

### Velocity Template Variables

- Velocity is a Java-based template engine
    - Part of the Apache Project
- Used in various connector properties as a placeholder
    for an object or variable value
- Syntax: ${objectName}
- Most Destination Mappings are Velocity template
    variables

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^59)
(^)


**NOTES**

### Message Statistics

- Dashboard shows cumulative statistics for channel
- Each channel can be expanded to show stats for each individual connector with
    the channel
- Channel groups show cumulative statistics for all channels in each group

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^60)


**NOTES**

### Message Statistics

- Statistics can also be cleared (reset to zero)
    - Does not remove actual message data
    - Clear statistics for all channels in a group, an entire channel,
       or an individual connector
    - Select individual columns to reset
    - Only clears current statistics

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^61)
Clear Statistics


**NOTES**

### Message Statistics

- Dashboard can display either _Current Statistics_ or _Lifetime Statistics_
    - Current statistics – stats since the last reset
    - Lifetime statistics – stats since channel was first created
       - Persist across resets
       - Clear lifetime stats on Server tab of Settings view (all channels)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^62)
Current/Lifetime^
Statistics


**NOTES**

### Viewing Processed Messages

- Channel Messages view displays historical message data for each channel
    connector
       - Select _View Messages_ in Dashboard or Channels view
       - Each message includes a “connector message” for each connector that executed
          - Data for the message as processed through a connector
       - Each message has a unique, sequential ID
       - Displayed columns are configurable

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^63)
(^)


**NOTES**

### Viewing Processed Messages

- Message details – click message to view
    - Messages tab
       - Displays message content in various states
          - Raw, Processed Raw, Transformed, Encoded, Sent, Response, Response Transformed, Processed
             Response
       - Will only display message content that exists
       - Option to format messages (XML & JSON)
          - For viewing purposes only—does not affect actual message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^64)
(^)


**NOTES**

### Viewing Processed Messages

- Message details (continued):
    - Mappings tab
       - Displays any Mapper variables available to the selected connector (user- or connector-created)
          - Scope (variable map)
          - Variable name
          - Variable value

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^65)
(^)


**NOTES**

### Viewing Processed Messages

- Message details (continued):
    - Errors tab
       - Displays exception information for any errors
       - Only displayed if errors exist
       - Three types of errors:
          - Processing, Postprocessor, Response

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^66)
(^)


**NOTES**

### Viewing Processed Messages

- Message data can be searched/filtered
    - By default, displays all messages
    - Results are paginated
       - Configurable page size
       - Controls to move to previous/next page, jump to specific page

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^67)


**NOTES**

### Viewing Processed Messages

- Search options:
    - Date/Time
       - Range, open-ended range, all day
    - Text Search
       - Literal text search on all message content (inefficient)
       - Option to search using regular expressions
          - Only supported when using PostgreSQL, Oracle, or MySQL as backend database
       - Can’t be used if message data is encrypted
    - Message Status (FILTERED, SENT, etc.)
    - Advanced Search Filter

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^68)
(^)


**NOTES**

### Viewing Processed Messages

- Advanced Search Filter:
    - Search in specific connectors
    - Message ID range
    - Import ID range
    - Server ID
    - Send Attempts range
    - Has attachment
    - Has error
    - Search in specific message content type
       (inefficient)
    - Search by custom metadata

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^69)
(^)


**NOTES**

### Viewing Processed Messages

- Messages can also be reprocessed
    - _Reprocess Results_ reprocesses all messages returned by filtered search
    - _Reprocess Message_ reprocesses only the selected message
    - Reprocessing provides the option to only
       process through selected destinations, and to
       overwrite existing messages and update statistics

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^70)
Reprocess Options


**NOTES**

### Viewing Processed Messages

- _Overwrite existing messages and update statistics_ option
    - When not selected (default), processes as if a new message
       - New rows added to message table
       - Dashboard statistics incremented
    - When selected, updates the existing message data
       - Original Received Date maintained, Received Date
          updated
       - Dashboard statistics updated

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^71)
(^)


**NOTES**

### Removing Messages

- Message data can be removed
    - Permanently removes message data from Connect’s backend database
    - _Remove All Messages_ removes all messages processed by the channel
    - _Remove Results_ removes only messages returned by filtered search
    - _Remove Message_ removes only selected individual message
       - Removing source message also deletes all destination data

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^72)
Remove Messages
Options


**NOTES**

### Removing Messages

- When removing all messages:
    - Channel must be stopped to remove the data
    - Option to temporarily stop channel
       - Channel will automatically be restarted after message data is removed
    - Option to also clear all statistics
- When removing individual messages:
    - Unfinished messages will only be removed if the channel is stopped

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^73)
(^)


**NOTES**

### Send Message Tool

- Send message directly to source connector,
    bypassing the actual connection
- Available in Dashboard, Channel Messages
    views
       - Tasks > Send Message
- Process either text message (e.g., HL7) or
    binary data
- Open file or copy-and-paste
- Opportunity to edit message before sending
- Send to selected destinations

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^74)
(^)


**NOTES**

### Web Administrator

- Web page providing access to:
    - Launch Connect Administrator
       - Uses Administrator Launcher, if installed
    - Download Administrator Launcher
    - Web Dashboard
- URLs to access:
    - [http://<hostname>:8080](http://<hostname>:8080)
       - 8080 is default HTTP Port
    - https://<hostname>:8443
       - 8443 is default HTTPS Port

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^75)


**NOTES**

### Web Dashboard

- View current or lifetime statistics
- Expand each channel to view individual connectors
- Launch Administrator
- Displays on mobile web browsers

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^76)


**NOTES**

# Message Processing

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^77)
(^)


**NOTES**

### Message Flow in a Channel

```
Transformed Encoded
```
```
Source
Connector
Destination
Connector
Transformed Encoded Sent
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^78)
Source
Receiver
Serializer

-^ to

```
XML
Filter
```
```
Serializer
```
-^ to

```
XML
```
```
Transformer
```
```
Filter
```
```
Deserializer
```
-^ from

```
XML
```
```
Transformer
```
```
Dispatcher
```
```
Deserializer
```
-^ from

```
XML
```
```
Destination
```
```
Raw
```
```
Raw
```

**NOTES**

### Message Transformation

- **Message transformation** is the process of serializing/deserializing the message data to/from
    XML for use in filters, transformers
       - Inbound message is serialized from the inbound data type to XML before filters and transformers
       - Transformed message data (XML) accessible in filters and transformers using JavaScript with E4X
       - Transformed message
          is encoded from XML
          to the outbound data
          type after transformers

```
Connector
Inbound
Data Type
```
```
Outbound
Data Type
Delimited Text Delimited^ Text^
DICOM DICOM^
EDI/X12 XML^ XML^ EDI/X12^
HL7 v2 HL7 v2
NCPDP NCPDP
XML XML
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^79)
Deserializer
Transformers
Filters
Serializer
XML Transformed
Message
(^)


**NOTES**

### Message Transformation

- Message transformation occurs for a connector when it meets any of the
    following conditions:
       - It has one or more filter rules
       - It has one or more transformers
       - The data type changes from inbound to outbound
       - The Outbound Message Template is set
- Otherwise, transformed message not generated
    - Channels with no transformed messages are known as “pass-through” channels

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^80)
(^)


**NOTES**

### Message States

- There are several different versions of the message as it flows through the
    connectors that can be persisted to the backend database
       - What is stored depends on selected message storage options
       - Different messages states viewable on Messages tab in Channel Message view
          - Only displays message states that are actually created

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^81)
(^)


**NOTES**

### Message States

- Possible Message States:
    - Raw
    - Processed Raw
    - Transformed
    - Encoded
       - Sent
       - Response
       - Response Transformed
       - Processed Response
    - Processed Raw will be covered later when discussing the Preprocessor Script
    - Response Transformed and Processed Response will be covered later in the “Responses”
       section

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^82)
(^)


**NOTES**

### Message States

- **Raw** – The message as it comes into the connector
    - In the source connector, this will be the original data received by the source connector
    - In a destination connector, this will be a copy of the source connector’s “Encoded” data
       - Each destination has its own copy of the message from the source connector
- **Transformed** – The intermediate XML representation of the message
    - Only exists under certain conditions
       - See Message Transformation
    - Generated from the Raw message data
    - Used in filters & transformers
    - Includes any changes made in transformers

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^83)
(^)


**NOTES**

### Message States

- **Encoded** – The message encoded in the outbound data type
    - If the message was transformed, the Transformed message encoded into the outbound data
       type
          - Includes any changes made to the Transformed message
    - Otherwise, a copy of the Raw message
- **Sent** – The actual data sent to the destination, as defined by the destination
    connector’s Template
       - Includes any variable replacements
       - May also include other information about the destination
          - For example, remote address/port, path of file generated, etc.
       - Only available in destination connectors

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^84)
(^)


**NOTES**

### Message States

- **Response** – Response message
    - In source connector, response message returned by the source connector (if source is set to
       return a response)
    - In destination connector, response message received from the destination

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^85)
(^)


**NOTES**

### Data Types and Properties

- Mirth Connect supports messaging using the following standard data types:
    - Delimited Text
    - DICOM
    - EDI/X12
    - HL7 version 2.x
    - HL7 version 3.0
    - JSON
    - NCPDP
    - Raw
    - XML

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^86)
(^)


**NOTES**

### Data Types and Properties

- Data types and associated properties
    for each connector can be set using
    the Set Data Types button/dialog on
    the Summary tab
       - Set inbound, outbound types for source
          connector
       - Set outbound type for destination
          connectors
       - Set inbound, outbound types for
          destination responses

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^87)
(^)


**NOTES**

### Data Types and Properties

- Data type settings define protocol used for conversion to/from transformed
    message
- Inbound, Outbound Properties define how conversion is done, based on the
    selected type
       - _Serialization_ properties define how the transformed XML is generated from the raw inbound
          message
       - _Deserialization_ properties define how the encoded outbound message is generated from the
          transformed XML
       - _Template Serialization_ properties define how the outbound message template is converted to
          XML (tmp)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^88)
(^)


**NOTES**

### Data Types and Properties

- Each data type has its own set of properties
    - Description of each property shown at bottom of dialog when selected
- Bulk Edit option available
    - Set data types, properties for multiple connectors at once
- Each destination connector’s inbound type will be the outbound type defined for
    the source connector

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^89)
(^)


**NOTES**

# Filters

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^90)
(^)


**NOTES**

## Filters

- Filters are composed of a series of rules which are evaluated as Boolean
    expressions
       - If rules collectively evaluate to true, message is _accepted_ by the connector
          - Connector’s transformer is executed after filter
          - Deserialization occurs after transformer
       - If rules collectively evaluate to false, message is _rejected_ by the connector
          - Connector’s transformer is not executed
          - Deserialization does not occur for that connector

```
HL7 HL7
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^91)
Connector
(^) XML XML XML
(^)
Deserializer
from XML
(^)
Transformer
(^)
Filter
(^)
Serializer
to XML


**NOTES**

### Filters

- Each connector has its own filters
    - If a message is rejected by the source connector, no destinations will process it
    - Filters on destination connectors can be used to “route” certain messages to specific
       destinations
          - If a destination connector’s filter rejects the message, it is not sent to that destination

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^92)
(^)


**NOTES**

### Filters

- Multiple rules can be combined with logical AND/OR operators
    - Click operator circle to change
- Rules can be disabled/enabled
    - Only enabled rules will be evaluated

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^93)


**NOTES**

### Filters

- Types of filter rules:
    - Rule Builder
       - Simple rules
       - Easy to create with drag-and-drop
    - JavaScript/External Script
       - Write your own code for complex rules
       - Covered in JavaScript section

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^94)
(^)


**NOTES**

### Filters

- Rule Builder
    - Create automatically by
       dragging from a node in the
       Inbound Message Template
       Tree into the filters list area
    - Or create manually via
       “Add New Rule” menu item

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^95)
(^)


**NOTES**

### Inbound Message Template

- What is an Inbound Message Template?
    - A sample message or message template
       - Message parsed into tree structure
    - Used only to provide drag-and-drop functionality for easy
       creation of basic filter rules and transformer steps
    - Does not restrict messages that can be accepted
    - Set in either Filter or Transformer view
    - Not required to create filter rules or transformers
    - Inbound message data always accessible within filter rules and
       transformer steps via the JavaScript variable msg
          - Represents the transformed version of the inbound message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^96)
(^)


**NOTES**

### Inbound Message Template

- **Demo:** Creating Rule Builder filter rules using the Inbound Message Template
    with drag-and-drop

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^97)
(^)


**NOTES**

### Rule Builder Filters

- Rule Builder
    - _Field_ is JavaScript/E4X code that defines the message value on which to filter
       - Automatically populated when created by dragging from a field in the Inbound Message Template
          Tree
       - Can contain JavaScript code/function calls
       - Must evaluate to a value (usually a string)
       - Do not end code with semicolon

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^98)


**NOTES**

### Rule Builder Filters

- Rule Builder (continued)
    - _Condition_ defines how to evaluate _Field_ value
       - Exists, Not Exist, Equals, Not Equal, Contains, Not Contain
       - Exists: _Field_ contains _any_ value
       - Not Exist: _Field_ is empty
       - All others use _Values_ list to compare against

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^99)


**NOTES**

### Rule Builder Filters

- Rule Builder (continued)
    - _Values_ list defines one or more values to compare _Field_ value against
       - Used for Equals, Not Equal, Contains, Not Contain
       - Can be string literal or variable
       - Comparison is case-sensitive
       - No defined limit to number of values

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^100)


**NOTES**

### Rule Builder Filters

- Rule Builder (continued)
    - Generated Script
       - View the internally-created JavaScript code for the rule (not editable)
       - Select/copy/paste allows code to be copied into a JavaScript filter

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^101)


**NOTES**

### Rule Builder Filters

- **LAB 4:** Create filters using Rule Builder
    - Create a channel with a TCP Listener (MLLP mode) source connector and two File Writer
       destinations
    - For source connector, only accept messages where:
       - MSH.4.1(sending facility) is “HOSPITAL A” or “HOSPITAL B”
          _- and -_
       - MSH.9.1(message type) is “ADT”
    - Sending facility filter rule should be case-insensitive
       - Use toUpperCase() function call to “normalize” values
    - For destination connectors, send messages from Hospital A to first destination, messages
       from Hospital B to second destination
_(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^102)
(^)


**NOTES**

### Rule Builder Filters

- **LAB 4** (continued)
    - Send a set of messages that will test the filter conditions
    - Verify messages are filtered and routed as expected
       - File should only be written if sent from corresponding sending facility

```
Channel
outbox/Hospital A
```
```
File Writer
Filter
HL7
Inspector
```
```
MLLP
6662
```
```
(HOSPITAL A or
HOSPITAL B) TCP^ Listener^ outbox/Hospital^ B^
and ADT
File Writer
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^103)
(^)
(^)
**Filter**
HOSPITAL B
**Filter**
HOSPITAL A


**NOTES**

# Transformers

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^104)
(^)


**NOTES**

## Transformers

- Transformers are a series of steps executed in order, allowing access to
    message data
- Each connector has its own transformers
- Uses of transformers:
    - Data extraction
    - New message creation
    - Message modification
    - Other uses

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^105)
(^)


**NOTES**

### Transformers

- Data extraction
    - Store data from message in
       variables for use in destination
       connectors
    - Use Mapper transformer steps
       - Created automatically when
          dragging from Inbound Message
          Template Tree node to list area
       - Mapped variables available in
          Destination Mappings for destinations to which they are visible
       - Also available to filters and transformer steps which follow and are in scope
- **Demo:** Creating & using Mapper variables

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^106)


**NOTES**

### Mapper Transformers

- Mapper transformer
    - Creates variable by storing variable data (name, value) into a “map”
       - Selected map defines variable’s scope
       - Five available maps for creating variables: Connector, Channel, Global Channel, Global, Response

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^107)
Add to Map


**NOTES**

### Mapper Transformers

- Maps available for Mapper variables
    - In most cases, use Channel Map (default) or Connector Map for Mapper transformer steps
    - Although available as an option, Global Map, Global Channel Map, and Response Map are
       not typically used in Mapper transformer steps
          - We’ll discuss use of these maps later

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^108)
(^)


**NOTES**

### Mapper Transformers

- Maps available for Mapper variables
    - **Connector Map** – Variables are only available within the connector in which they are
       defined:
          - Transformer steps that follow within the same connector
          - Connector’s template fields (if the connector is a destination)
    - **Channel Map** – Variables are available for the remaining processing of the message:
       - Transformer steps that follow within the same connector
       - Connector’s template fields (if the connector is a destination)
       - All filters, transformers, and destination template fields for destination connectors that follow
       - The channel’s Postprocessor script

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^109)
(^)


**NOTES**

### Mapper Transformers

- Maps available for Mapper variables
    - Connector Map and Channel Map variables only exist during the processing of a single
       message
    - Variable values are stored in Connect’s backend database along with message data
       - Can be viewed on Mappings tab in Channel Messages view

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^110)
(^)


**NOTES**

### Mapper Transformers

- _Mapping_ property in Mapper step is JavaScript/E4X code that

defines the value to use

- Where you’re getting the data from
    - Essentially, a “right-hand side” value
- Can also be a string literal
    - Use single _or_ double quotes
- Can include JavaScript function calls
- Must evaluate to a value (usually a string)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^111)
Mapping


**NOTES**

### Mapper Transformers

- Additional options for Mapper steps:
    - _Default Value_ – Specifies value to use instead of _Mapping_ when value identified by _Mapping_
       is empty or does not exist in the message
    - _String Replacement_ – Use regular expressions to perform string replacements on the
       _Mapping_ value when storing to the Mapper variable
          - Supports string literals or variable references for the _Regular Expression_ and _Replace With_ values
          - Can be used as a “translation table”

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^112)


**NOTES**

### Mapper Transformers

- Generated Script
    - View the internally-created JavaScript code for the step (not editable)
    - Select/copy/paste allows code to be copied into a JavaScript transformer

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^113)


**NOTES**

### Mapper Transformers

- **LAB 5:** Create a plain text patient report using Mapper transformer steps
    - Create channel with TCP Listener, File Writer
    - File Writer:
       - Extract data from PID segment with Mapper steps
       - Use report template in File Writer
       - Drag Mapper variables into template to create patient report

```
/outbox
```
```
HL7
Inspector
```
```
HL7
MLLP 6663
t Patient^ Report^
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^114)
Channel
TCP Listener
(^) HL7
File Wri
er
**TransformersMapper**^
demographicExtract^ patient data^
into channelvariables map


**NOTES**

### Transformers

- New Message Creation
    - Construct a new message from data in the inbound message
    - To create a new message:
       1.

```
2.
3.
```
```
Set outbound data type for connector to desired type for new message
Set Outbound Message Template to template for new message
Create a Message Builder transformer step for each piece of data to copy from inbound
message to Outbound Message Template
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^115)
(^)


**NOTES**

### Outbound Message Template

- What is an Outbound Message Template?
    - Defines the actual outbound message before transformation
       (Encoded Data)
    - Only use when transforming from one message type to another
       - In other words, only when creating a new message from the inbound
          data
    - Set in Transformer view

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^116)
(^)


**NOTES**

### Outbound Message Template

- What is an Outbound Message Template? (continued)
    - Drag from Inbound to Outbound Message Template Tree to populate
       - Creates Message Builder transformer step
    - Outbound Message Template referenced via JavaScript variable tmp
       - Represents the transformed version of the Outbound Message Template
       - Only defined if Outbound Message Template is set
    - Any values in the Outbound Message Template that are not
       overwritten with transformers will remain
          - Can be used for static/default values
- **Demo:** Using the Outbound Message Template with
    Message Builder steps to construct a new message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^117)


**NOTES**

### Message Builder Transformers

- Message Builder transformer
    - Created automatically when dragging from field in Inbound Message Template Tree to field
       in Outbound Message Template Tree
    - Copies data from inbound element in msg to outbound element in tmp
    - _Mapping_ property in Message Builder step is JavaScript/E4X code that defines value to use
       - Same as _Mapping_ property in Mapper step
    - _Message Segment_ property is JavaScript/E4X code that defines to where to write the value
       - Essentially, a “left-hand side” value
       - Do not use toString() method

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^118)


**NOTES**

### Message Builder Transformers

- Message Builder supports same additional options as Mapper step:
    - Default Value
    - String Replacement
    - Generated Script

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^119)
(^)


**NOTES**

### Outbound Message Template

- The generation of the encoded message is affected by the Outbound Template
    - If outbound template is set, the
       encoded message will be the
       **outbound template** with any
       transformations
- If outbound template is _not_
set, the encoded message
will be the **incoming message**
with any transformations

```
Transformed (msg)
```
```
Outbound Encoded^
Message
Template
```
```
Transformed (tmp)
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^120)
Template
Serializer

-^ to

```
XML
```
```
Filters
```
```
Message
```
```
Builder
```
```
Transformers
```
```
Deserializer
```
-^ from

```
XML
```
```
Raw
Raw Transformed (msg) Encoded
```
```
Se
```
```
ria
```
```
lize
```
```
r^
```
-^ t

```
o^ X
```
```
ML
```
(^) –^ fr
om
XML
(^)


**NOTES**

### Message Builder Transformers

- **LAB 6:** Create new XML message from HL7 data using Message Builder steps
    - Create channel with TCP Listener, File Writer
    - File Writer:
       - Extract patient ID from PID of HL7 with Mapper step
       - Create new XML document for patient data
       - Use given XML template as outbound template
       - Use Message Builder steps to populate XML doc

```
/outbox
```
```
HL7
Inspector
```
```
HL7
MLLP 6664
t XML^
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^121)
Channel
(^)
TCP Listener
(^)
(^) HL7
File Wri
er
(^) **Message Builder**
Copy data from PID **Transformers**^
inboundsegment of HL7 message into^
messageXML^ outbound template^


**NOTES**

### Transformers

- Message Modification
    - Modify some of the data in the inbound message before sending it to a destination,
       _without_ creating a new message
    - Common simple modifications:
       - Set a message component to a constant value
          - For example, change MSH.3.1 to “Mirth Connect”
       - Modify an existing value in a message component
          - For example, convert patient’s name to all uppercase
       - Copy a value from one message component to another
          - For example, copy patient ID in PID.3.1 to PID.2.1

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^122)
(^)


**NOTES**

### Transformers

- Message Modification
    - Use Message Builder transformer step
       - Right-click on node in Inbound Message Template Tree and select
          _Map to Message_
       - Alternatively, drag from tree into transformer list while pressing
          Control (Ctrl) key
    - Can also use JavaScript/External Script transformer steps
    - Do not use an Outbound Message Template

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^123)
Map to Message


**NOTES**

### Transformers

- Message Modification
    - _Map to Message_ option sets _Message Segment_ to selected component in inbound message
       (msg) – not tmp
    - _Mapping_ left blank
       - Provide value to put into specified message
          component
    - To change the component to a constant value
       for all messages, enter string into _Mapping_
          - Surround text with either double or single quotes

```
Mapping with
Constant Value
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^124)
(^)


**NOTES**

### Transformers

- Message Modification
    - To copy a value from one message component to another:
       - Create Message Builder using _Map to Message_ for component to change
       - Drag from node in the Inbound Message Template Tree from which to get the value
       - Drop into empty Mapping field

```
Mapping with Source Value
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^125)


**NOTES**

### Transformers

- Message Modification
    - To modify an existing value in a message component (make uppercase, truncate, etc.):
       - Create Message Builder using _Map to Message_ for component to modify
       - Drag from the same node in the Inbound Message Template Tree that you wish to modify
       - Drop into empty Mapping field
       - Add necessary code to modify
          the value

```
Mapping with toUpperCase() method
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^126)


**NOTES**

### Transformers

- Message Modification
    - Examples of simple value modification in _Mapping_ :
       - Convert value to all uppercase:
          msg['PID']['PID.5']['PID.5.1'].toString() **.toUpperCase()**
- “Conrad” becomes “CONRAD”
       - Truncate a date/time to only include date:
          msg['PID']['PID.7']['PID.7.1'].toString() **.substring(0,8)**
- “20201021143915” becomes “20201021”
       - Add time value onto a date:
          msg['PID']['PID.7']['PID.7.1'].toString() **+ "000000"**
- “20201021” becomes “202021021000000”
       - Remove dashes from a Social Security Number:
          msg['PID']['PID.19']['PID.19.1'].toString() **.replace(/-/g,**
- “741- 01 - 2606” becomes “741012606”

```
"")
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^127)
(^)


**NOTES**

### Transformers

- Where should modifications be performed?
    - If a channel has multiple destinations:
       - To have changes reflected in all destinations, modify the message in the source transformer
       - If changes are specific to a destination, modify the message in that destination’s transformer
    - If a channel has only one destination:
       - Message can be modified in either the source or destination transformer

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^128)
(^)


**NOTES**

### Transformers

- **LAB 7:** Modify values in message using Message Builder steps, send modified
    message to destination
       - Create channel with TCP Listener, File Writer
       - In source transformer, create Message Builders using _Map to Message_ method to:
          - Overwrite a component with a constant value
          - Copy a value from one component to another
          - Modify existing component values
       - Write modified message to file

```
HL7 /outbox^
```
Inspector (^) HL7
MLLP 6665
t HL7^
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^129)
Channel
TC
Lis
P
tener
(^)
(^) HL7
File Wri
er
(^) **Message Builder**
Use **Transformers** Map to Message^
values in MSH andmethod to modify^
PID segments


**NOTES**

# Automatic Mapper Variables

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^130)
(^)


**NOTES**

## Automatic Mapper Variables

- In addition to Mapper variables that you create in your transformers, Mirth
    Connect may also automatically create Mapper variables during message
    processing
       - Source Map variables
       - “mirth” Connector Map variables
       - Response Map variables

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^131)
(^)


**NOTES**

### Source Map Variables

- Some source connectors may create additional variables containing information
    about how the data was received
       - Examples:
          - TCP Listener: localAddress, localPort, remoteAddress, remotePort
          - File Reader: originalFilename, fileDirectory, fileSize
- This information is stored in Source Map variables
    - Source Map and its variables are read-only
    - Complete listing of Source Map variables available in the Mirth Connect Programming
       Reference

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^132)
(^)


**NOTES**

### Mirth Variables

- All connectors automatically create three Connector Map variables based on
    the processed message data:
       - mirth_source – The source from which the message was sent
          - For HL7 v2.x, MSH.4.1 (Sending Facility)
       - mirth_type – The message type
          - For HL7 v2.x, concatenation of MSH.9.1 (Message Type) and MSH.9.2 (Trigger Event)
          - Example: ADT-A08
       - mirth_version – The message version
          - For HL7 v2.x, MSH.12.1 (Version ID)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^133)
(^)


**NOTES**

### Mirth Variables

- All three mirth_* variables are available for drag-and-drop
    - In filters and transformers:
       - From Reference list, under
          Message Functions
    - In Destinations:
       - From Destination Mappings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^134)


**NOTES**

### Response Map Variables

- All destinations automatically create a Response Map variable
    - Variable name is the destination ID
       (e.g., d1, d2)
    - Variable value contains four parts:
       - Status – Status of message
          - SENT, ERROR, FILTERED, QUEUED, etc.
       - Status Message – Text indicating success/failure
          - Basic error message, “Message successfully sent”, etc.
       - Error Message – Detailed message if error occurred
          - Typically includes full stack trace
       - Message – Actual response from destination
          - HL7 ACK, HTTP response, SOAP response, etc.
          - Not all destinations will have a response message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^135)
**Response Map
Variable**
Status
Status Message
Error
Message


**NOTES**

### Response Map Variables

- Viewing Response Map Variable data

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^136)
Message
Status Status Message
**Response Map
Variable**
Status
Status Message
Error
Message
Variable name Status Status Message


**NOTES**

### Response Map Variables

- Viewing Response Map Variable data
    - Response errors will appear on Errors tab
    - Only visible if an error occurred

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^137)
Error
**Response Map
Variable**
Status
Status Message
Error
Message


**NOTES**

# Custom Metadata

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^138)
(^)


**NOTES**

## Custom Metadata

- Searching message data using the Text Search option has two drawbacks:
    - It can be slow
       - Searches through all message data (all content, all variable maps, etc.)
- It is inexact
- Example:
- Find all messages for a patient with last name “Fillmore”
- Problem: Text Search would return messages with “Fillmore” anywhere in the message (City, Attending
Doctor Last Name, etc.)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^139)
Text Search


**NOTES**

### Custom Metadata

- Custom Metadata addresses these problems by allowing you to identify
    message data values commonly used in message searches
       - Adds a new column to a message custom metadata table for the channel in Mirth Connect’s
          backend database
       - Based on Mapper variables created in transformers
       - SOURCE, TYPE always created by default
          - Based on mirth_source, mirth_type variables
       - Create on channel’s Summary tab

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^140)


**NOTES**

### Custom Metadata

- With Custom Metadata, searching is now on a specific
    value (or values) in an indexed database column
       - Custom metadata search under
          Advanced options
- Custom Metadata also displayed in message table in
    Channel Messages view
- **Demo:** Creating a custom metadata column from
    Mapper variable, viewing/searching data

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^141)
Custom MetadataAdvanced Search (^)


**NOTES**

# Introduction to E4X

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^142)
(^)


**NOTES**

## Introduction to E4X

- Filters & transformers operate on the **transformed** message
- The transformed message is an XML representation of the message data
    - All data types are serialized to XML
       - Except for JSON and Raw data types
- E4X is the syntax used to access data in the XML transformed message
    - ECMAScript for XML

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^143)
(^)


**NOTES**

### Introduction to E4X

- We’ve already used E4X:
    - Rule Builder filters
    - Mapper transformer
       steps
    - Message Builder
       transformer steps

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^144)


**NOTES**

### Introduction to E4X

- E4X uses square bracket notation to navigate the hierarchy of an XML
    document
       - Each set of square brackets identifies a child element in the XML

msg['PID']['PID.5']['PID.5.1'].toString()

- In filters & transformers, **msg** & **tmp** are variables representing XML objects
    - **msg** is the transformed XML for the inbound message
    - **tmp** is the transformed XML for the outbound message template
       - Only defined if outbound message template is set

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^145)
(^)


**NOTES**

### Introduction to E4X

- Example:
    - E4X to get patient’s last name (family name) from inbound
       HL7 message

```
msg['PID']['PID.5']['PID.5.1'].toString()
```
- **msg** is the entire message
- **msg['PID']** is the Patient Identification segment
- **msg['PID']['PID.5']** is the Patient Name field
- **msg['PID']['PID.5']['PID.5.1']** is the Family Name
    component

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^146)
**<HL7Message><MSH>** (^)
**<MSH.1>|</MSH.1><MSH.2>^~\&amp;</MSH.2>** (^)
**<MSH.3>** (^) **<MSH.3.1>ADTSENDER</MSH.3.1>
</MSH.3>...
</MSH><PID>
<PID.1>** (^) **<PID.1.1>1</PID.1.1>
</PID.1><PID.2>
</PID.2><PID.2.1>1001</PID.2.1>
...<PID.5>** (^)
**<PID.5.1>O'HALLAHAN</PID.5.1><PID.5.2>COLLEEN</PID.5.2>
</PID.5><PID.5.3/>
<PID.6/><PID.7>
<PID.7.1>19850704</PID.7.1></PID.7>
<PID.8>** (^) **<PID.8.1>F</PID.8.1>
...</PID.8>
</PID><NK1>
<NK1.1>** (^) **<NK1.1.1>1</NK1.1.1>
</NK1.1><NK1.2>
<NK1.2.1>O'HALLAHAN</NK1.2.1><NK1.2.2>BRITTANY</NK1.2.2>
</NK1.2><NK1.2.3>M</NK1.2.3>
</NK1> ...**^
**<PV1>** (^) **...
</HL7Message></PV1>**^


**NOTES**

### Introduction to E4X

- Example:
    - E4X to get patient’s last name from inbound XML
       message

```
msg['name']['last'].toString()
```
- **msg** is the entire message
- **msg['name']** is the <name> element
- **msg['name']['last']** is the <last> child element of <name>
- In both examples, toString() at end of E4X code
returns the contents of the specified XML element
as a String object

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^147)
**<patient><patientId>1001</patientId>** (^)
**<name>** (^) **<last>O'HALLAHAN</last>
</name><first>COLLEEN></first>
<dateOfBirth>19850704</dateOfBirth><gender>F</gender>
<nextOfKin><last>O'HALLAHAN</last>** (^)
**<first>BRITTANY</first><relationship>M</relationship>** (^)
**</nextOfKin><phoneNumber/>
</patient>**


**NOTES**

### Introduction to E4X

- If the XML contains multiple instances of an element, an index can

be used to identify a specific instance

- Indexes are zero-based
- Examples:

msg['nextOfKin'][0]['first'].toString()

- BRITTANY

msg['nextOfKin'][1]['first'].toString()

- PHILIP

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^148)
**<patient><patientId>1001</patientId>** (^)
**<name>** (^) **<last>O'HALLAHAN</last>
</name><first>COLLEEN></first>
<dateOfBirth>19850704</dateOfBirth><gender>F</gender>
<nextOfKin><last>O'HALLAHAN</last>** (^)
**<first>BRITTANY</first><relationship>M</relationship>** (^)
**</nextOfKin><phoneNumber/>
<nextOfKin><last>FRY</last>** (^)
**<first>PHILIP</first><relationship>S</relationship>** (^)
**</nextOfKin><phoneNumber>555 - 1234</phoneNumber>**^
**</patient>**


**NOTES**

# Channel Organization

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^149)
(^)


**NOTES**

### Channel Groups

- Channels can be organized into groups
    - Logical groupings of related channels

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^150)


**NOTES**

### Channel Groups

- Most channel actions can be applied to an entire channel group
    - Deploy/Undeploy
    - Enable/Disable
    - Import/Export
    - Start/Stop/Pause
    - Clear Statistics
    - Remove All Messages
- Select _New Group_ from Group Tasks menu to create a new group (Channels
    view)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^151)
(^)


**NOTES**

### Channel Groups

- By default, new channels are added to the “Default Group”
    - To move a channel to a different group:
       - Select channel, click _Assign To Group_ in Group Tasks menu (Channels view)
          _- or -_
       - Drag-and-Drop to desired
          group (Channels view)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^152)
(^)


**NOTES**

### Channel Groups

- Groups can be hidden from view
    - Both Channels and Dashboard views
    - Displays classic “flat” view
    - Toggle groups on/off using buttons at the bottom of the channel list
- **Demo:** Creating channel groups, assigning channels to groups

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^153)
Groups/Channels
Toggle


**NOTES**

### Channel Groups

- **LAB 8:** Create new channel group, assign channels to group, export
    - Create a new group called “Transformer Channels”
    - Assign the channels created in the three previous labs to the group, save changes
    - Export the channel group

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^154)


**NOTES**

### Channel Tags

- Channel Tags allow you to tag channels with arbitrary identifiers
    - Channels can then be filtered by tag(s) in either the Dashboard or Channels view
    - Each channel can have multiple tags
    - Independent of channel groups
       - Channels in different groups can have the same tag

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^155)


**NOTES**

### Channel Tags

- Tags can be added, edited, or removed in Settings view
    - Tags tab
    - Double-click name or color to edit

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^156)
(^)


**NOTES**

### Channel Tags

- Tags can also be applied to channels in Settings view
    - Apply tag changes to multiple channels at once

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^157)
(^)


**NOTES**

### Channel Tags

- Channels can be filtered by one or more tags in Dashboard and Channels
    views
       - Type tag name(s) in Filter field
       - Displays list of matching tag names as you type
       - If filter contains multiple tags, only displays channels with all tags entered (Boolean AND)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^158)
Channel Filter


**NOTES**

### Channel Tags

- Tags can be displayed as colored tag icons, tag names, or hidden

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^159)
Tag Name/Icon
Toggle


**NOTES**

### Channel Tags

- Tags can be added to or removed from a specific channel in Edit Channel view
    - Summary tab, Channel Properties
- Type tag name in _Tags_ field to add tag
    - If a tag with the given name does not already exist, a new tag will be created

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^160)


**NOTES**

### Channel Tags

- **Demo:** Using channel tags
    - Creating, editing tags
    - Applying tags to channels
    - Filtering channels by tags in Dashboard, Channels views

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^161)
(^)


**NOTES**

# Connectors

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^162)
(^)


**NOTES**

## Connectors

- Connect to external systems using a standard protocol (TCP, MLLP, HTTP, File)
- Each channel has one source connector, one or more destination connectors
- Each connector has its own:
    - Filters
    - Transformers
    - Message templates
    - Inbound/outbound data types
    - Properties

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^163)
(^)


**NOTES**

### Connectors

- Source Connectors
    - Channel Reader
    - DICOM Listener
    - Database Reader
    - File Reader
    - HTTP Listener
    - JMS Reader
    - JavaScript Reader
    - TCP Listener
    - Web Service Listener
       - Destination Connectors
          - Channel Writer
          - DICOM Sender
          - Database Writer
          - Document Writer
          - File Writer
          - HTTP Sender
          - JMS Writer
          - JavaScript Writer
          - TCP Sender
          - SMTP Sender
          - Web Service Sender

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^164)
(^)


**NOTES**

### Source Connectors

- Categories of source connectors:
    - TCP socket listener
       - Listens for incoming connections on a TCP socket
    - Polling reader
       - Periodically polls a data source for new messages
    - Connectors that are not a TCP socket listener or polling reader
       - Channel Reader, JMS Listener

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^165)
(^)


**NOTES**

### Source Connectors

- Common properties available for all source connectors:
    - Source queue
    - Response selection
    - Batch processing
    - Max processing threads

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^166)


**NOTES**

### Source Responses

- All source connectors can optionally return a response
    - Options:
       - None
       - Auto-generate
       - Use response from a destination
       - Use response returned from Postprocessor script
    - TCP Listener defaults to Auto-generate, all others default to None
    - Source Queue setting affects response options and when response is generated/sent

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^167)
(^)
(^)
(^) Response Selection


**NOTES**

### Source Responses

- Response examples:
    - Auto-generate:

```
Inbound HL7
MessageSender MLLP
HL7 ACK
```
- Choose when to respond:
    - Before processing, after source transformer, or after all destinations

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^168)
Channel
TC
P Listener
Destinatio
n


**NOTES**

### Source Responses

- Response examples:
    - Use response from destination:

```
Inbound HL7
MLLP
```
```
HL7
MessageSender MLLP DestinationSystem
HL7 ACK HL7 ACK
```
- Responses will be covered in greater detail later in the class

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^169)
Channel
TC
P Listener
HL7
(^) HL7 ACK
TCP Send
er


**NOTES**

### TCP Socket Listeners

- Source connectors that listen for incoming connections on a TCP socket
    - DICOM, HTTP, TCP, Web Service Listeners
- Common properties:
    - _Local Address_
       - Listen on all interfaces or a specific interface
          - If running on a server with multiple network interfaces
    - _Local Port_
    - **Note** : Combination of address and port must be unique for all channels and applications
       - If port is in use, channel will deploy, but not start

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^170)


**NOTES**

### TCP Connectors

- TCP Listener/TCP Sender
- Two transmission modes:
    - MLLP (default) – for HL7 v2 messages
    - Basic TCP – for any other message data
- Configure frame characters for either mode
- Process binary or text data

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^171)
(^)


**NOTES**

### TCP Connectors

- MLLP Transmission Mode
    - **M** inimal **L** ower **L** ayer **P** rotocol
    - For sending/receiving HL7v2 messages
    - Define frame characters
       - Defaults to standard MLLP frame characters:
    - Supports MLLPv2 – can be used for HL7 v3
    - Drag-and-drop from Byte Abbreviations list to get
       hexadecimal codes for various characters

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^172)
Transmission Mode
Settings
0x0B (VT) HL7 Message 0x1C (FS) 0x0D (CR)


**NOTES**

### TCP Connectors

- Basic TCP Transmission Mode
    - For sending/receiving any non-HL7 data
    - Define start/end frame characters
    - Use available Byte Abbreviations
- Either transmission mode displays selected
    sample frame
       - Example: <VT> _<Message Data>_ <FS><CR>

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^173)


**NOTES**

### TCP Connectors

- TCP Listener:
    - Can act as server or client
       - Determines which side establishes the connection
       - Data always sent to TCP Listener
       - Use server mode in most cases
    - Define max number of concurrent connections
    - _Receive Timeout_ value
       - Only use in Basic TCP mode if no frame characters defined
       - Defaults to 0 (wait indefinitely for EOM sequence)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^174)


**NOTES**

### TCP Connectors

- TCP Listener (continued):
    - By default, response will be sent using same connection
       on which data was received
    - Option to send response on new connection
       - Specify response address and port
    - Option to only send response on new connection during
       message recovery
          - For example, if recovering from system failure
    - Source Map variables related to the TCP connection:
       - localAddress
       - localPort
       - remoteAddress
       - remotePort

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^175)


**NOTES**

### TCP Connectors

- TCP Listener (continued):
    - Server Mode vs. Client Mode
    - Server Mode:
       - TCP Listener acts as server
       - Source system establishes
          connection to TCP Listener
       - Source system sends message
    - Client Mode:
       - TCP Listener acts as client
       - TCP Listener establishes
          connection to source system
       - Source system sends message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^176)
**Client Mode**
Channel
Source (^) TCP Connection TCP Listener
System M
(server) (client)^
**Server Mode**
Channel
Source
System M^
TCP Connection (^) TCP Listener
(client) (server)^


**NOTES**

### TCP Connectors

- TCP Sender:
    - Can act as client or server
       - Determines which side establishes the connection
       - Data always sent by TCP Sender
       - Use client mode in most cases
    - Define Remote Address, Port
    - Ability to override local socket binding
       - Can be used with a “virtual” IP address
    - Keep connection open, or close connection
       after message sent
          - If kept open, option to check if the remote host
             has closed the connection before sending

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^177)


**NOTES**

### TCP Connectors

- TCP Sender (continued):
    - Define how long to wait for response, or ignore
       response altogether
    - Option to queue message on response timeout
       - Only if queuing is enabled
    - _Template_ field defines data to send over
       connection
    - Response Map variable:
       - Status Message: Message indicating message
          was successfully sent, or error message if send
          failed
       - Message: Actual response data (e.g., HL7 ACK)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^178)


**NOTES**

### TCP Connectors

- TCP Sender (continued):
    - Client Mode vs. Server Mode
    - Client Mode:
       - TCP Sender acts as client
       - TCP Sender establishes connection
          to destination system
       - TCP Sender sends message
    - Server Mode:
       - TCP Sender acts as server
       - Destination system establishes
          connection to TCP Sender
       - TCP Sender sends message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^179)
**Server Mode**
Channel
TCP Sender TCP^ Connection^ Destination
(server)
M (^) System
(client)
**Client Mode**
Channel
TCP Sender (^) M TCP^ Connection^ DestinationSystem
(client) (^) (server)


**NOTES**

### TCP Connectors

- **Demo:** Walkthrough of connector settings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^180)


**NOTES**

### TCP Connectors

- **LAB 9:** Receive, send messages using TCP connectors in MLLP mode
    - Add Message Builder transformer step in source connector to overwrite Sending Application
       (MSH.3.1) to your student number (sX)
    - Send to destination system on port 9100 (use address from Student Information handout)
    - Respond from destination’s response
    - Send message to channel using HL7 Inspector
    - Verify message processed by channel and response received in HL7 Inspector

```
HL7
Inspector Inbound^ HL7^
MLLP 6666
```
```
Outbound HL7
MLLP 9100
```
```
Destination
System
(TCP
```
HL7 ACK HL7 ACK (^) Listener)
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^181)
Channel
TCP
Listen
er
HL7
HL7 ACK
TCP Se
nder
**Message
Builder**
Set MSH.3.1 of **Transformer**^
msg to “sX”


**NOTES**

### Polling Readers

- Source connectors that periodically poll a data source for new data
    - File, Database, JavaScript Readers
    - Poll on a given interval, or once a day at a selected time, or using Cron scheduling
- Common properties:

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^182)


**NOTES**

### Polling Readers

- Poll on interval
    - Specify interval as milliseconds, seconds, minutes, or hours
    - Polling occurs at “round” interval
       - Example: Interval is 10 minutes, channel is started at 11:03. First poll is at 11:10, then at 11:20, etc.
    - Option to poll once on start
    - If message processing has not yet completed when next interval occurs, polling is skipped
       for that interval

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^183)


**NOTES**

### Polling Readers

- Poll at a time
    - Specify daily polling time
    - Option to also poll on channel start

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^184)


**NOTES**

### Polling Readers

- For either Interval or Time polling types, advanced settings available
    - _Active Days_
       - Specify days of week or day of month that polling is active
    - _Active Time_
       - Specify time range that polling is active each day, or all day (Interval polling type only)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^185)
(^)


**NOTES**

### Polling Readers

- Poll on a Cron schedule
    - Use Cron expressions to specify polling schedule
       - Mouseover on Cron Jobs table displays info for formatting
          Cron expressions
    - Ability to specify multiple expressions
    - Option to poll once on channel start

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^186)


**NOTES**

### File Connectors

- File Reader/File Writer
- Read/write files using one of six modes:
    - File: Local file system
    - FTP: FTP Server
    - SFTP: SFTP Server (Secure FTP)
    - Amazon S3 bucket
    - SMB: Windows Network Share/Samba
    - WebDAV: Web Server using HTTP/HTTPS
- Support both text and binary files

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^187)
(^)


**NOTES**

### File Connectors

- File Reader:
    - Polling connector
       - Looks for files that match a given filename filter pattern
          in a specified location (directory, etc.)
    - Filename filter pattern:
       - Use wildcard characters (*, ?) to match pattern
       - Multiple patterns in comma-separated list
       - Or use regular expressions
    - Files should be deleted or moved after processing

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^188)


**NOTES**

### File Connectors

- File Reader (continued):
    - Action settings – how files are moved/deleted
       - _After Processing Action_ – move/delete file after
          processing has completed (after Postprocessor)
             - Even if errors occur in connectors
       - _Error Reading Action_ – move/delete file if file read error
       - _Error in Response Action_ – move/delete file if response returned by source (as specified in “Source
          Settings” has ERROR status)
             - Defaults to _After Processing Action_
       - For any action, if moving, specify directory, file name
          - 7 predefined variables available for use in those settings:
             ${channelName}, ${channelId}, ${DATE}, ${COUNT}, ${UUID}, ${SYSTIME}, ${originalFilename}

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^189)


**NOTES**

### File Connectors

- File Reader (continued):
    - Source Map variables related to the processed file:
       - fileDirectory
       - fileLastModified
       - fileSize
       - originalFilename

- (^) Source Map variables related to polling:

- pollId – A GUID uniquely identifying the poll from which the file was read
- pollSequenceId – The sequential position in the poll of the message
    - First message in the poll will always have ID 1
- pollComplete – Only present for the final message in the poll, with value always true

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^190)
(^)


**NOTES**

### File Connectors

- File Writer:
    - _Template_ defines data to write to file
       - Freeform text, can include Mapper variables
    - Option to keep connection to destination system
       open, or close after file written
          - If kept open, specify idle time after which connection
             is closed
    - If file exists, option to append (default), overwrite,
       or mark as error
    - Response Map variable
       - Status Message: Text indicating path of file written
          - Example:
             File successfully written: /Training/outbox/MyFile.txt
       - Message: Not used

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^191)


**NOTES**

### File Connectors

- Advanced options available for FTP, SFTP, SMB,
    Amazon S3 modes
       - Access by clicking tool button to right of mode selection
       - SMB settings new in 3.9
- **Demo:** Walkthrough of connector settings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^192)
(^)


**NOTES**

### File Connectors

- **LAB 10:** Create a channel with file connectors that reads files from a local
    folder and writes the file to an SFTP server
       - Read files from /Training/inbox
       - Move processed files to /Training/processed
          - Use ${channelName} variable to create subfolder in processed
       - Write file to outbox folder on SFTP server
       - Connect to SFTP using SFTP client
       - Deploy channel, copy files to inbox, verify files on SFTP server
          _(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^193)
(^)


**NOTES**

### File Connectors

- **LAB 10** (continued)

```
Channel
```
/Training/inbox (^) /files/outbox
SFTP Server
*.hl7 HL7 Address
File Reader File Writer
/Training/processed
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^194)


**NOTES**

### Database Connectors

- Database Reader/Database Writer
- Supports any database with JDBC driver
- Database drivers included with default installation:
    - Sun JDBC-ODBC Bridge, MySQL, Oracle, PostgreSQL, SQL Server/Sybase, SQLite
- Supports either basic SQL mode or JavaScript mode

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^195)
(^)


**NOTES**

### Database Connectors

- SQL Creation feature for easy code generation
    - Can be used to generate SELECT, UPDATE or INSERT
       statements
    - Option to filter for a subset of tables
    - Select columns to include in generated statement

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^196)
(^)


**NOTES**

### Database Reader

- Polling connector
- Generates messages from data
    returned by a database query
    (SELECT statement)
- One SELECT statement in SQL
    mode

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^197)


**NOTES**

### Database Reader

- Inbound data type is always XML when source connector is Database Reader
- One XML message generated for each row returned by query based on
    selected columns

• Example query: (^) • Example message:

- Inbound Message Template automatically set to XML message when query is
    defined or updated
- Additional option to aggregate all results into a single message (uncommon)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^198)
<result>
<col1>value</col1>
<col2>value</col2>
<col3>value</col3>
</result>
SELECT col1, col2, col3
FROM MyTable


**NOTES**

### Database Reader

- Option to run Post-Process SQL
    - Use to update the database so that the same data is not selected again on the next poll
    - Run once after all messages are processed, or after each individual message is processed
       - If run after each message, row’s values are available as variables for use in the Post-Process SQL
    - Executed at the end of message processing (after all destinations and postprocessor script
       have run)
          - Either for each message or for last message
    - One UPDATE statement in SQL mode

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^199)


**NOTES**

### Database Reader

- Option to run Post-Process SQL (continued)
    - If aggregating results, choose to run once for all rows, or for each row in results
    - In either case, execution occurs after the single aggregated result message is processed
       (after all destinations and postprocessor script have run)
    - If run for each row, that row’s values are available as variables for use in the Post-Process
       SQL

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^200)
(^)


**NOTES**

### Database Writer

- Insert or update data in the database
    - One INSERT/UPDATE statement in SQL mode
- Response Map variable:
    - Status Message: “Database write success, _n_ rows updated”
       - Or exception message if error occurred
    - Message: Not used
- **Demo:** Walkthrough of connector
    settings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^201)


**NOTES**

### Database Reader

- **LAB 11:** Generate HL7 messages from rows in a database table
    - Read unprocessed rows from NewPatients table
       - Where Processed column has value: false
    - Generate outbound HL7 message with data from database and write to file
       - Use outbound template and Message Builder steps
    - Mark each row read as processed with Post-Process SQL statement
       - Primary key in NewPatients table is NewPatientID
    - View contents of NewPatients table by connecting to database using SQL client
    - Deploy channel and verify results
       - One file containing an HL7 message generated for each row in NewPatients
       - Processed column in NewPatients table has been updated to true for each row
_(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^202)
(^)


**NOTES**

### Database Reader

- **LAB 11** (continued)

```
Database Reader
Database
Reader
```
```
File Writer
/Training/outbox
MessageTransformers Builder
SELECT * FROM
NewPatientsProcessed = false WHERE XML^ Copyinboundinto PID segment^ data^ messagefrom^ XML^ HL7^ HL7^
messageof^ outbound template^
Post-Process SQL
```
UPDATE NewPatientsSET Processed = true (^)
WHERE NewPatientID =
${newpatients_newpatientid}
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^203)
(^)
(^)


**NOTES**

### Database Writer

- **LAB 12:** Extract data from inbound HL7 messages, write data to database
    - Create Mapper variables for patient data from HL7 message
    - Use Database Writer to insert data into table
    - Verify that for each message processed through the channel, a new row created with the
       patient data from the message

```
Inbound HL7
HL7
Inspector
```
```
INSERT extractedvariables INTO
Patients table
```
```
MLLP
HL7 ACK
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^204)
(^) Database Writer
TCP Listener
(^)
(^) HL7
Database Writ
er
(^) Cr
vase (^)
**TransformersMapper**^
eateriables from channel PIDmap
gmentHL7 message of inbound


**NOTES**

### Document Writer

- Destination only
- Creates a PDF or RTF document
    - Document can be written to a file, into an “attachment”, or both
- Define page size
    - Select standard size or define
       custom values
- PDF files can be encrypted
    with password

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^205)


**NOTES**

### Document Writer

- Use HTML to create PDF or RTF formatting
    - Can include Cascading Style Sheets (CSS), inline styles
    - Not all HTML tags supported for RTF generation
    - Restrictions on HTML elements:
       - Tag names are case-sensitive, must be lowercase
       - All elements must be closed
          - Opening/closing tag pair or self-closing tag
       - Attribute minimization not supported
    - SAXParseException indicates malformed HTML

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^206)
(^)


**NOTES**

### Document Writer

- Document can be created as an attachment
    - What is an attachment?
       - An attachment is a part of the message data that is stored in
          Connect’s backend database separately from the message itself
             - Typically, some sort of binary data
       - An attachment has a token used to reference it
          - For example, in a subsequent destination
          - Example:
             ${ATTACH:9cb72e55-6dda-41ed-b2c2-fbc8e3bd8b93}
       - Attachment viewable in
          Channel Messages view

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^207)


**NOTES**

### Document Writer

- Response Map variable:
    - Status Message: Text indicating document written to attachment, file path, or both
       - Example:
          Document successfully written to attachment and file:
          /Training/outbox/MyFile.pdf
    - Message:
       - Attachment token if written to attachment
       - Not used if only writing to file
- **Demo:** Walkthrough
    of connector settings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^208)


**NOTES**

### Document Writer

- **LAB 13:** Generate a patient report PDF document using Document Writer
    - Generate PDF as both file and attachment
    - Use “PDF Patient Report Template.html” file for HTML code to format the PDF
       - Located in \Training\Miscellaneous
    - Include basic patient data from PID segment in HTML table
       - Extract from message using Mapper steps
       - Insert Mapper variables into proper
          location in HTML
       - Use patient ID for PDF file name

```
/outbox
and
Attachment
Inbound HL7 HTML^
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^209)
(^) PDF Writer
(^) Channel
Reader
(^)
(^) HL7
Document
Writer
(^) **TransformersMapper**^
Createvariables from channel maPI
segmentHL7 message of inboun
(^) p
Dd (^)


**NOTES**

### SMTP Sender

- Destination only
- Requires external SMTP server
    - Supply host, port, send timeout
    - Supports secure connection using TLS or SSL
    - Supports authentication
    - “Send Test Email” button verifies SMTP settings
- Can send to multiple email address
    - Separate multiple addresses with commas
- Body can be HTML or plain text

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^210)


**NOTES**

### SMTP Sender

- Ability to define any email headers
    - Example uses:
       - Specify CC or BCC addresses
       - Indicate high importance
       - Set follow-up flag
       - Use different reply-to address
    - Common headers listed in Programming Reference
- Files of any type can be attached
    - Specify attachment file name, content, MIME type
- Response Map variable:
    - Status Message: Text indicating email sent
       successfully (or error message)
    - Message: Not used

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^211)


**NOTES**

### SMTP Sender

- **Demo:** Walkthrough of connector settings, sending email with PDF attachment
    using the SMTP Sender
       - PDF Writer channel from previous lab, with SMTP Sender added as new destination
       - Includes some message patient data in the body
       - Uses email header to indicate high importance
       - Includes PDF as attachment
       - Available as Supplemental Lab 25

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^212)
(^)


**NOTES**

# Configuration Map

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^213)
(^)


**NOTES**

## Configuration Map

- Connector properties can use Mapper variables in addition to hard-coded
    values
       - Any connector property specified with a text field can use a variable
       - For example, IP address, port, directory, etc.
- The Configuration Map makes it easy to define these variables
    - Then reference in connector property field using standard Velocity variable syntax
       - Example: ${myFolderPath}

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^214)
(^)


**NOTES**

### Configuration Map

- Create configuration
    variables by adding entries
    to the Configuration Map
       - Similar to creating Mappers in
          transformers
       - Configuration Map tab in
          Settings view
       - Values can be obfuscated by
          unchecking _Show values_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^215)
(^)


**NOTES**

### Configuration Map

- Configuration Map scope is global
- Configuration Map variables are intended to be “static” values (rarely change)
    - If you need a global variable that can change dynamically, use Global Map variable
    - Values cannot be changed from transformers or scripts—only from Settings view
    - Changes are immediate upon saving
       - No need to redeploy or restart channels in most cases
          - TCP socket listeners must be restarted
- Configuration Map variable values are strings only
    - For other objects, use Global Map instead

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^216)
(^)


**NOTES**

### Configuration Map

- By default, variable definitions stored in properties file
    - In app data folder, configuration.properties
       - Name and location of file is configurable in mirth.properties

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^217)
# Path to folder for all files written by a File Writer
fileOutboxPath = /Training/outbox
filePrefix = training_
listenerAddress = 127.0.0.1
listenerPort = 6661


**NOTES**

### Configuration Map

- Variable definitions can also be stored in the backend database
- Storage location determined by configurationmap.location setting in
    mirth.properties
       - Value can be file (default) or database
       - If property is absent, defaults to file
- Regardless of storage location, variable data can be imported from or exported
    to any properties file

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^218)
mirth.properties
# Store Configuration Map values in backend database
configurationmap.location = database


**NOTES**

### Configuration Map

- **LAB 14:** Create Configuration Map variables, use in an existing channel
    - Create a few configuration variables (IP address, port, etc.)
    - Update the channel created in Lab 3 to use configuration variables in place of hardcoded
       values
    - Test to verify everything works the same

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^219)
(^)


**NOTES**

# Iteration

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^220)
(^)


**NOTES**

## Iteration

- What is iteration?
    - Iteration is the process of repeatedly executing one or more actions until some condition is
       met
    - This condition might be:
       - Executing the action(s) a specific number of times
       - Executing the action(s) for each item in a list or set
       - Executing the action(s) until a condition is true
    - Example:
       - Iterate over a list of all OBX segments in an HL7 message to extract observation value (OBX.5.1)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^221)
(^)


**NOTES**

### Iteration

- Scenario: We want to print some text multiple times
    - We could repeat the print action multiple times in sequence:

Start (^) **Output:**
I love Mirth Connect!
I love Mirth Connect!
I love Mirth Connect!
End
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^222)
Print “I love Mirth Connect!”
Print “I love Mirth Connect!”
Print “I love Mirth Connect!”


**NOTES**

### Iteration

- Iteration allows us to specify the action once, but execute it multiple times:

```
Start Counter^ Output^
```
```
1 I love Mirth Connect!
```
```
If counter <= false 2 I^ love^ Mirth^ Connect!^
maxValue (3) End^
```
```
true 3 I^ love^ Mirth^ Connect!^
```
```
4
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^223)
Increment counter by one
Print “I love Mirth Connect!”
Initialize counter = 1


**NOTES**

### Iteration

- Iteration may include the following:
    - A counter variable (index), initialized to some starting value (usually 0)
    - A Boolean condition that determines if iteration should continue
       - For example, if counter is less than some max value
    - The action(s) to be executed for each iteration
       - The “body” of the iteration
    - Increment of the counter variable

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^224)
(^)


**NOTES**

### Iteration in Mirth Connect

- Example uses of iteration in Mirth Connect:
    - To access data in an HL7 message:
       - In all segments
       - In specific repeating segments (OBX, NTE, AL1, etc.)
       - In repeating fields of a single segment (advanced)
       - In repeating fields of a repeating segment type (advanced)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^225)
(^)


**NOTES**

### Iteration in Mirth Connect

- Iterating over all segments in HL7 message

```
Start
```
```
i
if i < count of
segments
(3)
```
false (^) End 0
**1**
true 2
3
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^226)
Increment i by one
Access segment at index [i]
**HL7 Message
Index
Segments**
(^0) MSH|^~\&|ADT1|GENERAL HOSPITAL|||
(^1) EVN|A01|201708181123
(^2) PID||123456789|1922001||DIXON^CLYDE^S|
Initialize i = 0


**NOTES**

### Iteration in Mirth Connect

- Prior to Mirth Connect 3.5, iteration was only supported using JavaScript
    - For example, using for each loop
    - We’ll cover using JavaScript for iteration later
- Mirth Connect 3.5 added two new iteration features:
    - Iterator transformer group
    - Iterator filter group

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^227)
(^)


**NOTES**

### Iterator Transformer

- Iterator transformer step supports the same drag-and-drop functionality as
    Mapper and Message Builder transformer steps
- Is a “group” step
    - Groups one or more other transformer steps (Mapper, Message Builder,
       JavaScript) to be in the iteration
    - Can also include other Iteration steps for nested iteration
    - Uses an index to access each element in transformed XML message (msg)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^228)


**NOTES**

### Iterator Transformer

- Creating steps in an Iterator
    - When using drag-and-drop to create Mapper or Message Builder transformer steps, you will
       be prompted to add the step to an Iterator
          - Prompt can be disabled/enabled on the Administrator tab of the Settings view

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^229)
(^)


**NOTES**

### Iterator Transformer

- Creating steps in an Iterator
    - Iterator Wizard prompts you to select the part of the message on which you want to iterate
       - For example, segment level or field level
       - Defines where to apply the index

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^230)
(^)


**NOTES**

### Iterator Transformer

- Iterator transformer properties:
    - _Iterate On_ – Defines the element in the message (e.g., segment or field) on which to iterate
    - _Index Variable_ – The name of the index variable to use for iteration
       - By default, uses i, j, k...
       - Initialized to 0
    - _Drag-and-Drop Substitutions_ – Identifies the elements in the inbound message (msg) and
       outbound message template (tmp) that will be indexed in all steps that are part of the Iterator
       group

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^231)


**NOTES**

### Iterator Transformer

- Any steps added to an Iterator will automatically use the index defined when
    creating the Iterator
       - Example:

```
msg['IN1'] [i] ['IN1.4']['IN1.4.1']
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^232)


**NOTES**

### Iterator Transformer

- Example:
    - Message Builder for IN1.4.1 in Iterator
    - Iterator step defines _Index Variable_ as i, and _Drag-and-Drop Substitution_ for msg['IN1']
    - E4X in Message Builder step uses msg['IN1'][i] in place of msg['IN1']

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^233)


**NOTES**

### Iterator Transformer

- Iterators can contain multiple steps
    - When using drag-and-drop to create a new step, Iterator Wizard will prompt to add the step
       to a new Iterator or an existing one

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^234)


**NOTES**

### Iterator Transformer

- Deleting an iterator deletes all steps within it
    - Use Move Step Up/Move Step Down menu commands to move a
       transformer step out of an iterator
- Existing transformer steps not in an iterator can be added to
    an iterator using the Assign To Iterator menu command

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^235)
(^)


**NOTES**

### Iterator Transformer

- **Demo:** Using Iterator transformer to modify data in all DG1 segments
    - Truncate Diagnosis Date/Time (DG1.5.1) to have only date, without the time
       - yyyyMMddHHmmss - > yyyyMMdd
    - Example message:
    - Create Message Builder step on DG1.5.1 using “Map to Message”
    - Add to Iterator that iterates on msg['DG1']
    - Modify E4X in Mapping field of Message Builder to use JavaScript substring() function to
       truncate date to first 8 characters:
          msg['DG1'][i]['DG1.5']['DG1.5.1'].toString() **.substring(0,8)**

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^236)
MSH|^~\&|ADT1|GENERAL HOSPITAL|LABADT|MCM|201708181126|SECURITY|ADT^A01|...
PID||123456789|1922001^^^^AN^GH||DIXON^CLYDE^S^||19610615|M||2106-3|1200...
...
DG1|1|I9|1550|MAL NEO LIVER, PRIMARY|20170501103050|F||
DG1|2|I9|7843|APHASIA|20170708161020|A
DG1|3|I9|7840|HEADACHE|20170708161020|A
DG1|4|I9|7816|MENINGISMUS|20170708161020|A


**NOTES**

### Iterator Transformer

- Using an Iterator to build a message with Message Builder steps
    - Define where to apply the index in both the inbound message (msg) and
       outbound message template (tmp)
    - In this example, a new nextOfKin element (with child elements) will be
       created in tmp for each NK1 in msg

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^237)
<patient><patientId/> (^)
<name><last/> (^)
</name><first/>
<dateOfBirth/>
<gender/><nextOfKin> (^)
<last/><first/> (^)
<relationship/><phoneNumber/>
</patient></nextOfKin>


**NOTES**

### Iterator Transformer

- **LAB 15:** Use Iterator transformer with Message Builder steps to build message
    with repeating data
       - Channel receives HL7, outputs XML to file
       - Create Iterator to copy repeating next of kin data
          - Get data from NK1 segments, copy to nextOfKin elements
          - Use Message Builder steps to copy values from inbound message to outbound message template
             for each NK1
       - Also copy non-repeating patient demographic from PID
       - Send ADT messages with NK1 segments
       - Verify XML file generated with one nextOfKin element for each NK1 segment in inbound HL7
          message
          _(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^238)
(^)


**NOTES**

### Iterator Transformer

- **LAB 15** (continued)

```
Iterator Transformer Channel
```
```
/outbox
```
HL7 (^) Channel Reader HL7^ File Writer XML
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^239)
**Iterator Transformer**
inboundFor each NK1 in message, copy^
nextOfKin element indata from NK1 into^
XML outboundtemplate message
**MessageTransformers Builder**
segmentCopy data from PID of inbound HL7^
message into XMLoutbound message (^)
template


**NOTES**

### Iterator Filter

- The Iterator filter allows filtering to be performed on values in repeating
    segments or elements
       - Similar functionality to Iterator transformer
       - Is a “group” filter that can contain one or more Rule Builder or JavaScript filter rules

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^240)
(^)


**NOTES**

### Iterator Filter

- Creating filter rules in an Iterator
    - When using drag-and-drop to create Rule Builder filter rules, you will be prompted to add the
       rule to an Iterator
          - Prompt can be disabled/enabled on the Administrator tab of the Settings view

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^241)
(^)


**NOTES**

### Iterator Filter

- Creating filter rules in an Iterator
    - Iterator Wizard prompts you to select the part of the message on which you want to iterate
       - For example, segment level or field level
       - Defines where to apply the index
       - Same as Iterator for transformers

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^242)
(^)


**NOTES**

### Iterator Filter

- Iterator filter properties:
    - _Iterate On_ , _Index Variable_ , and _Drag-and-Drop Substitutions_ –
       - Same behavior as in Iterator Transformer
    - _Accept Message If_ –
       - **At Least One** of the iterations returns true
       - **All** of the iterations return true
    - _Break Early_ –
       - If **Yes** , stop iterating once condition is met (if _Accept Message If_ is set to **At Least One** ) or condition cannot be
          met (if _Accept Message If_ is set to **All** )
       - If **No** , will always execute all iterations

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^243)


**NOTES**

### Iterator Filter

- Any rules added to an Iterator Filter will automatically use the index defined
    when creating the Iterator
       - Example:

```
msg['AL1'] [i] ['AL1.4']['AL1.4.1'].toString()
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^244)


**NOTES**

### Iterator Filter

- **LAB 16:** Use an Iterator filter to only accept messages where patient is allergic
    to penicillin
       - Iterate over AL1 segments
          - AL1 (Patient Allergy Info) is a repeating segment
       - Accept message if at least one of the iterations is true
          - AL1.3.2 has value of “PENICILLIN”
          - Break early once found
       - Process some messages,
          verify results
             /outbox
HL7

Inspector (^) MLLP 6668
HL7
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^245)
(^) Iterator Filter Channel
TCP
Listener
(^)
File
Writer
**IteratorRule FilterBuilder with**
andIterate accept^ over message^ all^ AL1s^
if at least one AL1has value of
“PENICILLIN”AL1.3.2 in


**NOTES**

# Using JavaScript in Mirth Connect

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^246)
(^)


**NOTES**

### JavaScript in Mirth Connect

- Mirth Connect supports adding JavaScript to channels and other locations
    - Allows you to customize channels and support complex functionality
    - May also be necessary to handle certain messaging requirements
       - For example:
          - Iteration over repeating segments/elements (pre-3.5)
          - Adding new segments/elements
          - Deleting segments/elements

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^247)
(^)


**NOTES**

### JavaScript in Mirth Connect

- JavaScript in Mirth Connect:
    - JavaScript filters & transformers
    - Channel scripts (Deploy/Undeploy/Preprocessor/Postprocessor)
    - Global scripts (Deploy/Undeploy/Preprocessor/Postprocessor)
    - Batch processor
    - JavaScript connectors
    - Database connectors – JavaScript mode
    - Attachment handler
    - Code templates

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^248)
(^)


**NOTES**

### JavaScript Basics

- Variables
    var _variablename_ ;
       -- or - -
    var _variablename_ = _value_ ;
- Operator = assigns value to variable
- JavaScript is weakly typed
- No need to declare a variable’s type
- Unassigned variables have a value of undefined

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^249)
(^)


**NOTES**

### JavaScript Basics

- Variables (continued)
    - Examples:
       // Define variable
       var a = 5;
       // Define variable
       var b = 10;

```
a as number value 5
```
```
b as number value 10
```
```
// Define
var c = a
// Change
a = 25;
// Change
a = "ABC";
```
```
variable c as sum of a and b (15)
+ b;
value of a to number value 25
```
```
value of a to string "ABC"
```
```
// Define variable
var d = "DEF";
// Define variable
var e;
```
```
d as string "DEF"
```
```
e without assigning value (value is undefined)
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^250)
(^)


**NOTES**

### JavaScript Basics

- Adding comments to JavaScript code
    - Comments allow information about the code to be added to the script
    - Comments are not executable code
- JavaScript supports both single-line and multi-line comments:
    - Start single-line comments with two forward slashes
       // This is a comment.
    - Enclose multiple-line comments with /* and */
       /* This is a comment.
          This is part of the same comment. */

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^251)
(^)


**NOTES**

### JavaScript Basics

- Strings
    - Native object for representing text
    - Define a string using single or double quotes:
       var myString1 = "ABC";
       var myString2 = 'DEF';
    - Use + and += operators to concatenate strings
       myString1 += myString2 + "GHI";
       Result: “ABCDEFGHI”
- Equivalent to:
myString1 = myString1 + myString2 + "GHI";

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^252)
(^)


**NOTES**

### JavaScript Basics

- Strings (continued)
    - Use length property to get size (in characters)
       var size = myString1.length;
    - String object has several built-in methods:
       - charAt(), indexOf(), replace(), split(), substring(), toLowerCase(), toUpperCase(), etc.
    - Examples:
       var myString = "I love Mirth Connect!";
       // Make a copy of myString, converting to all uppercase
       var myStringUpper = myString.toUpperCase();
       // Get the first 12 characters of myString ("I love Mirth")
       var myString2 = myString.substring(0, 12);
       // Find the index of the word "Mirth" in myString (7)
       var index = myString.indexOf("Mirth");

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^253)
(^)


**NOTES**

### JavaScript Basics

- Arrays
    - Native object for representing a collection of elements
       var colors = ["blue", "red", "green", "orange"];
    - Access elements with 0 - based numeric index
       var firstColor = colors[0];
       var secondColor = colors[1];
       colors[3] = "yellow";

```
// "blue"
// "red"
```
- Use length property to count of elements
    // Get the count of elements in the array (4)
    var numColors = colors.length;
- Several built-in methods
    - concat(), reverse(), replace(), sort(), indexOf(), etc.
       // Get the index of "green" (2)
       var greenIndex = colors.indexOf("green");

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^254)
**colors
Index Value**
0 “blue”
(^1) “red”
(^2) “green”
3 “orange”


**NOTES**

### JavaScript Basics

- Conditional statements & comparisons
    - Used to conditionally execute blocks of code based upon one or more conditions
    - Syntax:
       if ( _condition1_ )
       {
          _// Code to execute_
       }
       else if ( _condition2_ )
       {
          _// Code to execute_
       }
       else
       {
          _// Code to execute_
       }
    - **else if** block is optional and can be repeated for multiple conditions
    - **else** block is optional
    - Curly braces ({}) delimit begin, end of code blocks to execute if condition is true

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^255)
(^)


**NOTES**

### JavaScript Basics

- Conditional statements & comparisons (continued)
    - In condition, use comparison operators to compare values:
       == (equals), != (not equals), < (less than), > (greater than), <= (less than or equal to), >= (greater than or equal to)
    - Can also use Boolean operators for multiple conditions:
       && (AND), || (OR),! (NOT)
    - Example:

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^256)
var// Triglycerides alertText = ""; level (^) under 150
if{ (triglycerides < 150)
} alertText^ =^ "good";^
//else Triglycerides if (triglycerides level exactly == 150) (^150)
{ (^) alertText = "borderline";
}// (^) Triglycerides level over 150 and under 500
else if (triglyceridestriglycerides < 500) > 150 &&
{ (^) alertText = "high";
}// (^) Triglycerides level 500 or higher
else
{ (^) alertText = "very high";
}


**NOTES**

### JavaScript Basics

- Functions
    - A function executes a sequence of statements to perform a specific task, and returns a value
       - Example:
          // Call a function that adds given
          var sum = addNumbers(5, 10, 100);
    - Parameters are optional
       - Example:
          // Call the same function with two

```
numbers and returns their sum
// Result is 115
```
```
numbers
var sum = addNumbers(5, 10); // Result is 15
```
- Objects may also have functions (methods)
    - For example, methods of the String object

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^257)
(^)


**NOTES**

### JavaScript & E4X in Mirth Connect

- E4X can be used in JavaScript filters and transformers to access and/or modify
    data in the transformed XML
       - XML variable (msg, tmp) represents root-level element (i.e., the entire document)
       - Use JavaScript bracket notation for each element level in the document below the root
       - Example:
          var sendingFacility = msg['MSH']['MSH.4']['MSH.4.1'].toString();

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^258)
(^)


**NOTES**

### JavaScript & E4X in Mirth Connect

- Dragging-and-dropping from the Message Template Trees into a JavaScript
    context provides the E4X code for that message data

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^259)
(^)


**NOTES**

### JavaScript & E4X in Mirth Connect

- Accessing HL7 message data with E4X
    - For most values in an HL7 message, go three levels deep
       - First level is segment
       - Second level is field within a segment
       - Third level is component within a field
       - Do this even if a field contains only one component

```
msg['PID']['PID.5']['PID.5.1'].toString()
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^260)
(^)


**NOTES**

### JavaScript & E4X in Mirth Connect

- Accessing HL7 message data with E4X
    - Exceptions to the three-level rule:
       - Message delimiters defined in MSH
          - Defined at field level (two levels deep)
          - MSH.1 = |
          - MSH.2 = ^~\&
          - Example:
             var fieldDelimiter = msg['MSH']['MSH.1'].toString();
       - Subcomponents
          - Four levels deep:
             msg['RXE']['RXE.1']['RXE.1.2']['RXE.1.2.1'].toString()
          - Parsing subcomponents is on by default
          - Components without subcomponents are still at third level

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^261)
(^)


**NOTES**

### JavaScript & E4X in Mirth Connect

- Some HL7 segments can have multiple repetitions within a single message
    - For example, OBR, OBX, NK1, IN1, NTE
- For repeating segments, use bracket notation after segment reference to index:
    - Example:
       var valueType5 = msg['OBX'] **[4]** ['OBX.2']['OBX.2.1'].toString();
    - Note: index and Set ID are different values
- To determine number of repetitions of a segment, use XML length() method:
    - Example:
       var obxCount = msg['OBX'].length();

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^262)
(^)


**NOTES**

### Iterating Over Message Segments

- Iteration may be required when accessing data in repeating segments
    - For example, to get data from all AL1 segments, regardless of how many are in the message
- Why iteration in JavaScript?
    - Iterator filters and transformers did not exist prior to Mirth Connect 3.5
    - Handle complex cases that may not be easy to implement using Iterator filters/transformers

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^263)
(^)


**NOTES**

### Iterating Over Message Segments

- Iteration in JavaScript
    - Two ways to iterate over segments:
       - Iterate over only a certain segment type (e.g., OBX)
       - Iterate over all segments in the message
       - Both methods use the JavaScript for each loop
          - Iterates over values in a list, such as an array or list of elements in an XML document
       - Both loops available as code templates:
          - Iterate Over Segment
          - Iterate Over All Segments

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^264)
(^)


**NOTES**

### Iterating Over Message Segments

- Iterating over named segments:
    - Use when getting data from only one segment type
       for each (seg in msg..OBX)
       {
          // Get observation value type from OBX.2.1
          var obsType = seg['OBX.2']['OBX.2.1'].toString();
       }
    - Will iterate for each instance of the given segment type in message
       - For example, if message contains six OBX segments, body of loop will execute six times
       - In the for each statement, msg..SEG returns a list of all segments in the message (as
          XML) with the given segment name

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^265)
(^)


**NOTES**

### Iterating Over Message Segments

- Iterating over all segments:
    - Use when getting data from multiple segment types
       for each (seg in msg.children())
       {
          if (seg.name().toString() == "OBR")
          {
             // Get placer order number from OBR.2.1
             var orderNum = seg['OBR.2']['OBR.2.1'].toString();
          }
          else if (seg.name().toString() == "OBX")
          {
             // Get observation value from OBX.5.1
             var obsValue = seg['OBX.5']['OBX.5.1'].toString();
          }
       }
    - Will iterate for all segments in message
       - In the for each statement, msg.children() returns a list of all segments in the message (as XML)
       - To determine current segment name as a string, call seg.name().toString()

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^266)
(^)


**NOTES**

### Iterating Over Message Segments

```
for each ( seg in msg..OBX)
{
var obsType = seg ['OBX.2']['OBX.2.1'].toString();
var obsValue = seg ['OBX.5']['OBX.5.1'].toString();
}
```
- Both loop types use a variable named seg
    - Defined by the loop code
    - Name is arbitrary—you can change it
    - Only in scope within and after the loop
    - For each iteration, seg is XML for that segment
       <OBX>
          <OBX.1>
             <OBX.1.1>1</OBX.1.1>
          </OBX.1>
          <OBX.2>
             <OBX.2.1>NM</OBX.2.1>
          </OBX.2>
          ...
       </OBX>

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^267)
(^)


**NOTES**

### JavaScript Transformers

- JavaScript transformer steps allow JavaScript code to be executed to access or
    modify message data
       - Logic can by much more complex than Mapper and Message Builder steps
       - Access/modify values in repeating segments
          - Prior to addition of Iterator Transformers in 3.5, this could only be done in JavaScript
       - Complex message modification
          - Creating new segments
          - Deleting segments
       - Execute equivalent functionality to Mapper, Message Builder steps

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^268)
(^)


**NOTES**

### JavaScript Transformers

- Two types of JavaScript transformers:
    - JavaScript: Code contained within Connect’s JavaScript transformer context
    - External Script: Code contained in external file (loaded at deployment)
- Create by clicking _Add New Step_ in menu
    - Then, select type

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^269)


**NOTES**

### JavaScript Transformers

- Creating Mapper variables in JavaScript
    - Put the value into the appropriate map, depending on desired scope
       - Channel Map, Connector Map, etc.
    - Same as a Mapper transformer step
    - JavaScript variable for each map
       - For example, channelMap, connectorMap
    - Call Map’s put() method to create variable
       - Example:
          channelMap.put("lastName", msg['PID']['PID.5']['PID.5.1'].toString());

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^270)
(^)


**NOTES**

### JavaScript Transformers

- What is a map?
    - An unordered data structure that maps unique keys to values
    - put() method adds a new entry into the map
       - Takes _key_ (variable name), _value_ (variable value) as parameters
       - Or updates an existing entry if key already exists
    - get() method returns the value from the map for a given key
       - Returns null if key not found in map
    - Example:
       // Put values into channel map
       channelMap.put("patientId", "12345");
       channelMap.put("lastName", "Fry");
       channelMap.put("firstName", "Philip");
       channelMap.put("dateOfBirth", "19720913");
       // Get value for "lastName" entry
       var ptLastName = channelMap.get("lastName");

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^271)
**Channel Map
Key Value**
“patientId” “12345”
“lastName” “Fry”
“firstName” “Philip”
“dateOfBirth” “19720913”


**NOTES**

### JavaScript Transformers

- Each variable map has “shortcut” functions to put/get
    - Same as calling standard put()/get() methods for each map

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^272)
**Map Variable Put Get**
Response Map
responseMap responseMap.put($r( _key_ , _value_ ) _key_ ,^ _value_ )^ responseMap.get($r( _key_ ) _key_ )^
Connector Map
connectorMap connectorMap.put($co( _key_ , _value_ ) _key_ ,^ _value_ )^ connectorMap.get($co( _key_ ) _key_ )^
Channel Map
channelMap channelMap.put($c( _key_ , _value_ ) _key_ ,^ _value_ )^ channelMap.get($c( _key_ ) _key_ )^
Source Map
sourceMap Not available sourceMap.get($s( _key_ ) _key_ )^
Global Channel Map
globalChannelMap
globalChannelMap.put( _key_ , _value_ ) globalChannelMap.get( _key_ )
$gc( _key_ , _value_ ) $gc( _key_ )
Global Map
globalMap globalMap.put($g( _key_ , _value_ ) _key_ ,^ _value_ )^ globalMap.get($g( _key_ ) _key_ )^
Configuration Map
configurationMap (^) Not available configurationMap.get( _key_ )^
$cfg( _key_ )


**NOTES**

### JavaScript Transformers

- You can create variables with the same name in multiple variable maps
- Function to get a variable value from any map:

$('myVar')

- Order of variable lookup for both $('myVar') and ${myVar}:

```
1)
2)
```
```
3)
```
```
4)
```
```
Response Map
```
```
Connector Map
Channel Map
```
```
Source Map
```
```
5)
6)
```
```
7)
```
```
Global Channel Map
Global Map
```
```
Configuration Map
```
- Resolves to first instance of variable found

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^273)
(^)


**NOTES**

### JavaScript Transformers

- What’s the difference between ${myVar} and $('myVar')?
- ${myVar} is a Velocity template variable
    - Used in connector property fields (e.g., Port, IP Address, File Name, etc.)
- $('myVar') is a JavaScript function
    - Used in JavaScript contexts (e.g., JavaScript Transformers/Filters, JavaScript Writer, etc.)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^274)
(^)


**NOTES**

### JavaScript Transformers

- Creating Mapper variables from data in repeating segments
    - Example problem:
       - We need the names of next-of-kin as “first last” from each NK1
       - For example:
          Philip Fry
          Yancy Fry
       - First name and last name are two separate components of NK1
       - Using a Mapper step within an Iterator group will create an array of values from a component for all
          segment instances
       - For example:
          NK1.2.1 (Family Name): [“Fry”, “Fry”]
          NK1.2.2 (Given Name): [“Philip”, “Yancy”]

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^275)
(^)


**NOTES**

### JavaScript Transformers

- Creating Mapper variables from data in repeating segments (continued)
    - Iterating in a JavaScript transformer allows you to format repeating segment data as needed
    - Example:
       var nextOfKin = "";
       for each (seg in msg..NK1)
       {
          nextOfKin += seg['NK1.2']['NK1.2.2'].toString() + " " +
             seg['NK1.2']['NK1.2.1'].toString() + "\n";
       }
       channelMap.put("nextOfKin", nextOfKin);

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^276)
(^)


**NOTES**

### JavaScript Transformers

- **LAB 17:** Use a JavaScript transformer to iterate over repeating message
    segments to extract data and generate a lab report
       - In JavaScript transformer:
          - Use JavaScript string variable to build formatted report text
          - Iterate over all segments
             - If OBR segment, include order number from OBR.2.1
             - If OBX segment, include observation name (OBX.3.2), value (OBX.5.1) and value units (OBX.6.1)
          - Put report string in channel map variable for use in File Writer
       - Send OUL (lab observation) message
       - Verify lab report file generated
          /outbox
Lab
HL7 Report

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^277)
(^) Channel
Chan
nel Reader
(^) HL7
**JavaScript**

- Create **Transformer** lab report^
    Wr

```
File
iter
```

**NOTES**

### JavaScript Transformers

- Simple message modification
    - To change a value in the message, use = operator
       - Equivalent functionality to Message Builder
    - Examples:
       // Overwrite Sending Application in MSH.3.1
       msg['MSH']['MSH.3']['MSH.3.1'] = "Mirth Connect";
       // Copy Patient ID in PID.2.1 to PID.3.1
       msg['PID']['PID.3']['PID.3.1'] = msg['PID']['PID.2']['PID.2.1'].toString();
       // Copy patient last name from inbound message to outbound message template
       tmp['name']['last'] = msg['PID']['PID.5']['PID.5.1'].toString();
    - Do not use .toString() on left-hand side of assignment
       - Hold down Alt key when dragging from the Inbound Message Template Tree to get the E4X code
          without .toString() at the end

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^278)
(^)


**NOTES**

### JavaScript Transformers

- Complex message modification
    - JavaScript transformers must be used to:
       - Add new segments to the message
       - Delete segments from the message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^279)
(^)


**NOTES**

### Adding Segments to a Message

- Options for adding segments to a message:
    - Create XML representing the new segment, then append after segment it should follow
       - Use += operator to insert into message after a particular segment
          // Add new empty segment ZZZ after existing
          msg['QRF'] += <ZZZ/>;
    - Use available built-in global functions:
       - createSegment(), createSegmentAfter()
       - Available from code templates in Reference tab
          - Message Functions category

```
segment QRF
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^280)
(^)


**NOTES**

### Adding Segments to a Message

- Global functions to create segments:
    - Create Segment (individual)
       XML createSegment(String segmentName)
- Creates an XML object for the segment with the given name
- Does not insert it into the message
- Returns a reference to the XML object
// Create XML for new segment ZYX
var newSeg = createSegment('ZYX');
// Set the value in ZYX.1.1
newSeg['ZYX.1']['ZYX.1.1'] = "My Value";
// Add segment to message after ZZZ segment
msg['ZZZ'] += newSeg;

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^281)
(^)


**NOTES**

### Adding Segments to a Message

- Global functions to create segments:
    - Create Segment (in message)
       XML createSegment(String segmentName, XML msg)
- Creates an XML object for the segment with the given name
- Inserts the segment XML at the end of the given message (i.e., as the last segment)
- Returns a reference to the XML object
// Create XML for new segment ZYX at the
var newSeg = createSegment('ZYX', msg);
// Set the value in ZYX.1.1
newSeg['ZYX.1']['ZYX.1.1'] = "My Value";

```
end of msg
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^282)
(^)


**NOTES**

### Adding Segments to a Message

- Global functions to create segments:
    - Create Segment After Segment
       XML createSegmentAfterSegment(
          String segmentName, XML afterThisSegment)
- Creates an XML object for the segment with the given name
- Inserts the segment XML after the specified segment
- Returns a reference to the XML object
// Create XML for new segment ZYX after segment ZZZ
var newSeg = createSegmentAfter('ZYX', msg['ZZZ']);
// Set the value in ZYX.1.1
newSeg['ZYX.1']['ZYX.1.1'] = "My Value";
- The above call to createSegmentAfter() is equivalent to:
msg['ZZZ'] += createSegment('ZYX');

```
in msg
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^283)
(^)


**NOTES**

### Adding Segments to a Message

- When building a new segment, best practice is to operate on the returned XML
    reference, not directly on msg (or tmp)
       - Returned reference “points” to that specific segment
       - No need to specify an index if segment being created is a repeating segment (NTE, OBX,
          AL1, etc.)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^284)
(^)


**NOTES**

### Adding Segments to a Message

- Example:
    - Add a new NTE (note) segment after the PID segment
    - Message may already contain other NTE segments

```
newSeg
```
- Incorrect code:
    // Create a new NTE and insert as the last segment in the message
    createSegmentAfter('NTE', msg['PID']);
    // This statement will fail without an index specified
    msg['NTE']['NTE.3']['NTE.3.1'] = "This is the note text";
- Correct code:
    // Create a new NTE and insert as the last segment in the message
    var newSeg = createSegmentAfter('NTE', msg['PID']);
    // This statement will always work, since newSeg refers to segment just created
    newSeg['NTE.3']['NTE.3.1'] = "This is the note text";

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^285)
**MSH** |^~\&|LABNET|Hospital A|...
**PID** |1|880040|||Conrad^Hermes^^|...
( **N** In **T** s **E** e|rt new NTE here)
**OBR** |1|928384443|056696622^LA|...
**OBX** |1|NM|1000735^CTNI||1.12|...
**NTE** |1||Note about OBX


**NOTES**

### Deleting Segments from a Message

- To delete a segment:
    - Use JavaScript delete operator/keyword

```
delete msg['OBX'];
```
- For repeating segments, above syntax will delete all instances of that
    segment
       - Use index to delete an individual repeating segment

```
delete msg['OBX'][0];
```
- When deleting from a list of repeating segments, remaining segments will be
    re-indexed after deletion
       - For example, the OBX at index 1 will be at index 0 after the deletion

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^286)
(^)


**NOTES**

### JavaScript Transformers

- **LAB 18:** Use a JavaScript transformer to add, delete segments
    - TCP Sender transformer:
       - Delete first OBX segment
       - Iterate over all remaining OBX segments and renumber Set ID in OBX.1.1
       - Add an NTE (note) segment with short note in NTE.3.1 after PID segment
       - Add a custom ZZZ segment at the end of the message
    - Send OUL (lab observation) message
    - Verify modified message received
       by HL7 Inspector

```
HL7
HL7 ModifiedHL7 Inspector^
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^287)
(^) Channel
Cha
nnel Reader
(^)
(^) HL7
Se
TCP
nder
**TransformerJavaScript**^

- •^ DeleteRenumber^ first^ SetIDsOBX^ segment in
    - remainingAdd NTE, ZZZ^ OBXs segments^


**NOTES**

### JavaScript Filters

- JavaScript filter rules allow any JavaScript code to be executed to evaluate
    data
       - Logic can be much more complex than what Rule Builder steps support
       - Filter on values in repeating segments
          - Prior to addition of Iterator Filters in 3.5, this could only be done in JavaScript
       - Perform database, table lookups, etc.
       - Perform less than/greater than comparisons on dates or numeric values
       - Execute equivalent functionality to Rule Builders

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^288)
(^)


**NOTES**

### JavaScript Filters

- Two types of JavaScript filters:
    - JavaScript: Code contained within Connect’s JavaScript filter context
    - External Script: Code contained in external file (loaded at deployment)
- Create by clicking _Add New Rule_ in menu
    - Then, select type

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^289)


**NOTES**

### JavaScript Filters

- Return true if message should be accepted; false if it should be rejected
    - Example:
       if (msg['MSH']['MSH.9']['MSH.9.1'].toString() == "ADT")
       {
          return true;
       }
       else
       {
          return false;
       }
    - If no return statement is included in code, default return value is false

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^290)
(^)


**NOTES**

### JavaScript Filters

- **Demo:** Using a JavaScript filter to only accept messages where patient is
    allergic to penicillin
       - Same functionality as Lab 15
       - Looks for value of “PENICILLIN” in AL1.3.2
          - AL1 (Patient Allergy Info) is a repeating segment
       - Uses for each loop to iterate over AL1 segments
       - Returns true if found
          - Returns false if not found only after seeing all AL1s
       - Available as Supplemental Lab 26

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^291)
(^)


**NOTES**

### JavaScript & E4X

- In addition to what we’ve see here, E4X provides several other operators and
    XML object methods for accessing and modifying data in XML documents
- For more information on E4X and the XML object:
    - [http://www.devx.com/webdev/Article/33393](http://www.devx.com/webdev/Article/33393)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^292)
(^)


**NOTES**

### Code Templates

- Provide templates for function calls and code snippets for
    performing common JavaScript tasks, stored in one location
- Available in all JavaScript contexts from Reference tab
    - Simple drag-and-drop functionality
    - Can also be accessed by pressing Ctrl+Space in code editor
- Dozens of built-in code templates available
- Ability to define custom code templates

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^293)


**NOTES**

# Global & Channel Scripts

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^294)
(^)


**NOTES**

### Global & Channel Scripts

- Set of scripts available for arbitrary use:
    - Deploy
    - Undeploy
    - Preprocessor
    - Postprocessor
- Each script available at both global- and channel-level scope
    - Global scripts executed for all channels
    - Channel scripts executed for corresponding channel
- Written in JavaScript

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^295)
(^)


**NOTES**

### Deploy Scripts

- JavaScript that is executed upon deployment of channels
    - Global Deploy script is executed when any channel is deployed (once per deployment)
    - Channel Deploy script is executed when that channel is deployed
    - Global Deploy script is executed _before_ channel Deploy scripts

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^296)
(^)


**NOTES**

### Deploy Scripts

- Used to perform any necessary setup required by channels, beyond
    Configuration Map variables
       - Configuration Map only supports string values
       - Use Deploy Script to create non-string Global Map or Global Channel Map variables
       - Example use cases:
          - Create shared connections
          - Load complex/large lookup data from an external database or file

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^297)
(^)


**NOTES**

### Global Map/Global Channel Map

- Global Channel Map variables
    - Create in a channel’s Deploy Script
    - Only available to that channel
    - Available in all parts of channel
       - Filters/Transformers of all connectors, channel scripts, etc.
- Persists across all messages processed by that channel
- Global Map variables
    - Create in global Deploy Script
    - Available to all channels, global scripts, etc.
- Neither map is persisted to the backend database
    - Values only exist in memory

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^298)
(^)


**NOTES**

### Undeploy Scripts

- JavaScript that is executed upon un-deployment of channels
    - Global Undeploy script is executed when any channel is un-deployed (once per
       un-deployment)
    - Channel Undeploy script is executed when that channel is un-deployed
    - Global Undeploy script executed _after_ all channel Undeploy scripts
- Used to perform any necessary cleanup
    - For example, to close any open connections or remove variables created in Deploy Script

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^299)
(^)


**NOTES**

### Deploy/Undeploy Scripts

- **Demo:** Channel that uses Deploy, Undeploy scripts with Global Channel Map
    variable
       - Channel’s Deploy Script:
          - Logs that channel is being deployed
          - Creates a JavaScript array of approved sending facilities
          - Puts array in Global Channel Map variable
       - JavaScript filter in source connector:
          - Only accepts messages if MSH.4.1 (Sending Facility) found in array in Global Channel Map
       - Channel’s Undeploy Script:
          - Logs that channel is being undeployed
          - Removes array from Global Channel Map

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^300)
(^)


**NOTES**

### Preprocessor Scripts

- JavaScript that is executed before the transformed message is created in the
    source connector
       - Global Preprocessor script is executed when any channel receives a message
       - Channel Preprocessor script is executed when that channel receives a message
       - Global Preprocessor script is executed _before_ channel Preprocessor script
- Used to make any necessary “fixes” to the message
    - For example, remove/replace invalid characters
    - In other words, make any necessary changes to the data so that it conforms correctly to the
       selected inbound data type

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^301)
(^)


**NOTES**

### Preprocessor Scripts

- Raw inbound message available as JavaScript variable message
    - The message in its native format (e.g., HL7 v2) as a String
- Script must return a String value
    - The message after any “fixes” (if necessary)
    - Must conform to source connector’s inbound data type
    - By default, returns message variable without any modifications

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^302)
(^)


**NOTES**

### Preprocessor Scripts

- If the Preprocessor Script alters the message, the modified data is stored as
    the Processed Raw message
- **Processed Raw** – One of the possible message states
    - Persisted to the backend database and viewable in the Channel Messages view
    - Only exists if message returned by Preprocessor script is different than the original Raw
       message
          - If Processed Raw exists, it is serialized to XML, not Raw
    - Only available in source connector

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^303)
(^)


**NOTES**

### Preprocessor Scripts

```
Transformed Encoded
```
```
To destination
connectors
```
```
Preprocessor
Script does
not modify
data
Preprocessor
Script
```
Processed Raw Transformed Encoded (^) **modifies data**
To destination
connectors
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^304)
Source
Source
Receiver
Receiver
Preprocessor
Script
Preprocessor
Script
Serializer

-^

```
to^ XML
```
```
Serializer
```
-^ to

```
XML
```
```
Filter
```
```
Filter
```
```
Transformer
```
```
Transformer
```
```
Deserializer
```
-^ from

```
XML
```
```
Deserializer
```
-^ from

```
XML
```
```
Raw
```
```
Raw
```

**NOTES**

### Preprocessor Scripts

- **Demo:** Using a preprocessor script to replace invalid segment delimiter
    characters (0x7F – DELETE) with the required carriage return characters
       - Use replace() function of the String class on message variable:
          message.replace(/\u007F/g, "\r");

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^305)
(^)


**NOTES**

### Postprocessor Scripts

- JavaScript that is executed after all destinations of a channel have completed
    - Global Postprocessor script is executed when any channel processes a message
    - Channel Postprocessor script is executed when that channel processes a message
    - Global Postprocessor script is executed _after_ channel Postprocessor script
- Executed even when no destinations are executed
- For example, when message filtered in source connector
- Can be used to handle enhanced acknowledgments and custom responses
    - Because the Postprocessor script is executed after all destinations, you have access to the
       response data (including response status and actual response message) for all destinations

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^306)
(^)


**NOTES**

### Postprocessor Scripts

- Every destination connector puts its response data into Response Map variable
    - Name is destination ID (e.g., “d1”, “d2”, etc.)
    - Value is Response object
- Get response object for destination using
    responseMap.get()
       - Then call “get” method for desired property
       - Example:
          // Get Response object for destination ID=1
          var r1 = responseMap.get('d1');
          // If response status is ERROR, log error message
          if (r1.getStatus() == "ERROR") {
             logger.error("Destination 1 error: " + r1.getError()");
          }

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^307)
**Response
Properties Methods**
status getStatus()
statusMessage getStatusMessage()
error getError()
message getMessage()


**NOTES**

### Postprocessor Scripts

- Postprocessor can optionally return a response
    - Source connector can respond from Postprocessor
    - For example, to return a response from a routed destination
    - Not common
    - Example:
       var r1 = responseMap.get('d1');
       var r2 = responseMap.get('d2');
       if (r1.getStatus() == "SENT") {
          return r1;
       }
       else if (r2.getStatus() == "SENT")
          return r2;
       }

```
{
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^308)
(^)


**NOTES**

# Responses

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^309)
(^)


**NOTES**

## Responses

- All source connectors can generate, and possibly return a response
- Three options for responding:
    - Auto-generate an ACK
       - Applies to HL7 v2.x only
    - Respond from a destination
    - Respond from Postprocessor script

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^310)


**NOTES**

### Auto-Generated ACKs

- Three different types of auto-generated ACKs:
    - Successful, error, rejected
    - Type determines what is used for ACK’s acknowledgement code (MSA.1.1) and text
       message (MSA.3.1)

```
MSH|^~\&|RECAPP||NEXTGEN|General Hospital|20160907151024||ACK^A01^ACK|20160907151024|P|2.4
MSA| AE |24553| An Error Occurred Processing Message.
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^311)
**Type ACK Code (MSA.1.1) Text Message (MSA.3.1)**
Successful AA
Error AE An Error Occurred Processing Message.
Rejected AR Message Rejected.


**NOTES**

### Auto-Generated ACKs

- Generated ACK properties can be
    configured in the Inbound Properties
    of the Set Data Types dialog
       - HL7 v2.x data type only
       - Set ACK code (MSA.1.1) and
          text message (MSA.3.1) for
          successful, error, and rejected ACKs

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^312)
(^)


**NOTES**

### Auto-Generated ACKs

- Choose when/how to generate, return ACK
    - Before processing
       - Always generates a “successful” ACK
    - After source transformer
       - ACK generated based on source connector only
          - If source accepts message without error, generates “successful” ACK
          - If source filters message, generates a “rejected” ACK
          - If the source encounters an error, generates an “error” ACK
_(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^313)
(^)


**NOTES**

### Auto-Generated ACKs

- Choose when/how to generate, return ACK (continued)
    - Destinations completed
       - ACK generated based on what happens in all destinations, using precedence of destination
          statuses
             - ERROR (highest), SENT, FILTERED (lowest)
             - If any destination experiences an error, generates an “error” ACK
             - If any destination successfully sends and no destinations experience an error, generates a “successful” ACK
             - If all destinations were filtered, generates a “rejected” ACK
             - **Note:** For the purpose of auto-generating an ACK, a status of QUEUED is considered the same as SENT

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^314)
(^)


**NOTES**

### Response Validation

- All destination connectors support the option to validate its response
    - Validating the response sets the message status based on the acknowledgement code
       (MSA.1) in the returned ACK, and optionally the Message Control ID
    - Only supported for HL7 v2.x
    - On by default for TCP Sender, off for all others

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^315)
(^)
(^)
(^)
Validate Response


**NOTES**

### Response Validation

- Settings for how to validate the ACK are set in the Response Validation section
    of the Set Data Types dialog
       - ACK Codes:
          - Successful ACK Codes set
             destination’s status to SENT
                - Default: AA,CA
          - Error ACK Codes set
             destination’s status to ERROR
                - Default: AE,CE
          - Rejected ACK Codes set
             destination’s status to ERROR
                - Default: AR,CR

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^316)
(^)


**NOTES**

### Response Validation

- Response Validation Settings (continued)
    - Message Control ID
       - Validates that the control ID returned in MSA.2.1 matches the original message control ID
       - Original ID can be from the destination’s encoded data (MSH.10.1), or from a Mapper variable
       - If no match, destination’s status set to ERROR
- Validation options only apply when _Validate Response_ is set to “Yes” for that
    destination
       - If set to “No”, ACK is ignored and status is always marked as “SENT” (assuming successful
          connection)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^317)
(^)


**NOTES**

### Response Transformers

- Responses from destinations can be transformed using Response
    Transformers
       - Works the same as normal transformers, except msg is now the response from the
          destination
       - Same step types available (Mapper, Message Builder, JavaScript, Iterator, etc.)
       - Each destination has a response transformer

```
Outbound message
(e.g., HL7 ADT)
```
```
Destination
System
Response message
(e.g., HL7 ACK)
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^318)
Destination Connector
Response
Transformer
Transformer


**NOTES**

### Response Transformers

- Example uses:
    - Use Mapper steps to extract data from response for use in subsequent destinations
    - Modify the response from a destination before it is returned by the source connector
       - Modify data in the response message itself
       - Modify the status, status message, or error message of the destination’s response object
    - Use an outbound template with Message Builder steps to create a new response message
       from the actual response data
          - For example, build an HL7 ACK from data in an XML response

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^319)
(^)


**NOTES**

### Response Transformers

- If one or more response transformer steps are defined, the
    serialization/deserialization process occurs for the response message
       - The transformed response is available as JavaScript variable msg

```
Transformed Response (msg) Response
```
```
Available to select
as response in
source connector
```
- Select the destination in the source connector’s Response selector to respond with the
    destination’s processed response

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^320)
Deserializer

-^

```
from
```
```
XML
```
```
Response
```
```
Transformer
```
```
Serializer
```
- to

```
XML
```
```
Destination
```
```
System
```
```
Processed
Response
```
(^)


**NOTES**

### Response Transformers

- Response-related message states:
    - **Response Transformed** – Intermediate XML representation of response from destination
       - Only exists when a destination connector has response transformers and response has been
          transformed
    - **Processed Response** – The response after any transformations
       - Only exists when a destination connector has response transformers and response has been
          transformed
- Source connector’s response will include any changes made in the response
    transformer if responding from that destination

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^321)
(^)


**NOTES**

### Response Data Types and Properties

- To set data types and
    serialization properties for
    response for a destination:
       - Set Data Types dialog
       - Expand destination, select
          Response
       - Set Inbound/Outbound data types
       - Set Serialization/Deserialization
          properties for response
          transformation

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^322)
(^)


**NOTES**

### Response Transformers

- The response transformer makes it easy to get or modify the status, status
    message, or error message of the response, without having to directly access
    the Response Map variable
       - Provides the following variables:
          - responseStatus
          - responseStatusMessage
          - responseErrorMessage
       - Available in Reference list
          - Response Transformer category
       - Example:

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^323)
if (responseStatus == ERROR && msg['MSA']['MSA.1']['MSA.1.1'].toString() == "AR")
{
responseStatus = SENT;
responseStatusMessage = "Rejected by destination";
}
**Response Property Response Transformer Variable**
status responseStatus
statusMessage responseStatusMessage
error responseErrorMessage
message msg


**NOTES**

### Response Transformers

- **Demo:** Walkthrough of response transformers and example uses

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^324)
(^)


**NOTES**

### HL7 Queries

- HL7 supports query messages and responses
    - Query another system for data, destination system responds with
       requested data if available
    - Examples:
       - Query for matching patients/patient demographic data
       - Query for results of an observation
       - Query for list of vaccinations for a patient

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^325)
(^)


**NOTES**

### HL7 Queries

- Query message has a QRD (Query Definition) segment
    - Defines the parameters for the query
       - For example, patient name, date of birth, gender, SSN, etc.
- May also have an optional QRF (Query Filter) segment
    - Defines optional filters
       - For example, only patients with a date of birth within a defined date range
- Query response messages are like ACKs, but with additional data
    - Usually include MSA (Message Acknowledgement) segment
    - May include QAK (Query Acknowledgement) segment
       - Identifies if data was found, how many matches, etc.
    - Will also include segments for the data requested (if found)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^326)
(^)


**NOTES**

### HL7 Queries

- Examples
    - QRY-A19/ADR-A19 – Patient Query/Response
       **QRY-A19 Patient Query (for demographics) ADR-A19 ADT Response (with demographics)**
    - VXQ-V01/VXR-V03 – Query for Vaccination Record/Response

```
VXQ-V01 Query for Vaccination Record VXR-V03 Vaccination Record Response
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^327)
**MSH** |^~\&|RecApp|RecFac|SendApp|SendFac|20201112110219||VXR^V03|98765|P|2.5
**MSAQRD** |AA|3784625187||202021103022813|R|I|QID3784||||423 (^) - 18 - 8822^Zoid^Harold^|VXI^VACCINE INFO^||
**PID** |15822043|26878943262||Jenkins^Michelle^||19750419|F||2106- 33002 Silverman St.^...
**PD1RXA** |U|A||088021^Bashir^Julius^D^^Dr.^MD|N||N|Y|N||||||DNR|A|20191111|1|1|20171018||90632^ **Hepatitis A vaccine, adult dosage** ^CPT|1||||019238^Ogawa^Alyssa (^)
**RXA** |2|1|20171018||90746^ **Hepatitis B vaccine, adult dosage** ^CPT|1||||019238^Ogawa^Alyssa
**MSH** |^~\&|SendApp|SendFac|RecApp|RecFac|202021103144100||VXQ^V01|3784626923|P|2.5
**QRD** |202021103144100|R|I|QID3784|||| **378 - 77 - 0042^Jenkins^Michelle^|VXI** ^VACCINE INFO^||
**MSH** |^~\&|HDH|DOOP-HIE|RECAPP|Omicron Clinic|20201016114807||ADR^A19|123456|P|2.5
**MSAQAK** |AA|1029384756||QID013678543| **OK** (^) |1|||
**QRDPID** |1|12345|12345^^^^MRN||FRY^PHILIP^J||19711015|M||1|1969|20201014084216|R|I|QID013678543||||920- 13 - 1213^Fry^Philip^^^^^^SSA^^^^SSN|DEM|||T TOBOR WAY^^NEW (^) YORK...
**PD1** |U|A||001122^ZOIDBERG^JOHN^A^^DR.^MD|N||N|Y|N||||||DNR|A|20180517
**MSH** |^~\&|ADTSENDER|Omicron Clinic|HDH|HIE|20201014084216||QRY^A19|1029384756|P|2.5
**QRD** |20201014084216|R|I|QID013678543|||| **920 - 13 - 1213^Fry^Philip^^^^^^SSA^^^^SSN** | **DEM** |||T


**NOTES**

### Response Transformers

- **LAB 19:** Create a channel that sends an HL7 query for patient demographics,
    and generates a patient report from data in response
       - TCP Sender destination sends QRY-A19 (Patient Query) message to destination system
       - Destination system responds with ADR-A19 (ADT Response)
          - If destination system has demographics for patient, response will have:
             - MSA.1.1 (Acknowledgement Code) value “AA” (accepted)
             - QAK.2.1 (Query Response Status) value “OK” (data found)
             - PID and PD1 segments containing the patient’s demographic data
          - If destination system does not have demographics for patient, response will have:
             - MSA.1.1 (Acknowledgement Code) value “AA” (accepted)
             - QAK.2.1 (Query Response Status) value “NF” (not found)
          - If message type other than QRY-A19 sent to destination system, response will have:
             - MSA.1.1 (Acknowledgement Code) value “AR” (rejected)
       _(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^328)
(^)


**NOTES**

### Response Transformers

- **LAB 19** (continued)
    - Response transformer uses Mappers to extract data from ADR-A19 response:
       - MSA.1.1 (Acknowledgement Code)
       - QAK.2.1 (Query Response Status)
       - Basic patient demographic data from
          PID (name, gender, data of birth, etc.)
    - File Writer destination

```
Channel
TCP Sender HL7 QRY-A19
Destination
Response System^
```
**Transformer** (^) MLLP 9102
Only
accepts
QRY-A19
extractUse^ Mappers ACK code,^ to^
Channel (^) query status, and
Reader patient^ data^ HL7 ADR-A19

- Has filter to only write file
    if response had “AA” for
    MSA.1.1 and “OK” for QAK.2.1
- Writes demographic data from
    response to patient report text file
       - Same as Lab 5

```
HL7 QRY-A19 HL7 QRY-A19
```
File Writer (^) /outbox
**Filter** Patient Report
ACKOnly write code equals^ file^ if^
status“AA” and query equals “OK”^
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^329)


**NOTES**

# Mapper Variable Review

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^330)
(^)


**NOTES**

## Mapper Variable Review

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^331)
**Map Scope Where Typically Set Typical Usage**
Response Map

- Filterstemplates for all destination connectors rules, transformer steps, destination
- executed after definitionPostprocessor script
- • DatabaseResponse Generation settings Reader’s Post-Process script
    - Automatically by destination
    - connectorsPostprocessor^ Script
    - JavaScript transformer

```
Destination response data
```
```
Connector Map
```
- Transformersame connector steps following definition within
- Destinationdefined in destination transformer template within same connector if
- Responsesource transformer Generation settings if defined in
    - Mapper transformer
    - JavaScript transformer

```
Connector-specific message data
```
```
Channel Map
```
- Transformersame connector steps following definition within
- Filterstemplates for all destination connectors rules, transformer steps, destination
- executed after definitionPostprocessor script
- • DatabaseResponse Generation settings Reader’s Post-Process script
    - Mapper transformer
    - JavaScript transformer

```
Message data
```
```
Source Map
```
- Allscripts parts of channel except Deploy and Undeploy
    - Automatically by some source
       connectors, including batchprocessor

```
Information about how source connector
received message, batch information
```
```
Global Channel Map
```
- All parts of the channel in which it is defined
    - Channel Deploy Script
       Non-configuration values/objects available
       for all messages to a single channel

```
Global Map
```
- • AllGlobal parts scripts of all channels
- Alerts
    - Global Deploy Script
       Non-configuration values/objects available
       throughout Connect
Configuration Map
- • AllGlobal parts scripts of all channels
- Alerts
- Configuration Map tab in Settings
view

```
Static configuration settings
```

**NOTES**

# Internal Routing

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^332)
(^)


**NOTES**

## Internal Routing

- The ability to pass messages from
    one channel to another within
    Connect
- Also known as “channel chaining”
- Use dedicated Channel Reader,
    Channel Writer connectors

#### C

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^333)
Channel
C
F

#### T

#### C

#### C C C

#### T

#### F


**NOTES**

### Internal Routing

- Example use case:
    - Multiple senders
       - Each requires a unique connection (IP address/port)
       - However, action taken one message as received is the same for all senders (e.g., extract data and
          write to database)

(^9001) TCP Channel^1 Channel
Sender (^1) Listener (^) Writer
“Main”
Channel
(^9002) TCP Channel^2 Channel
Writer
Channel
Reader
Sender 2 DB^
Listener Writer
(^9003) TCP Channel^3 Channel
Sender (^3) Listener Writer
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^334)
(^)


**NOTES**

## Channel Configuration

- Channel Reader:
    - Allows a channel to only listen for new messages from other channels
       - Or from Send Message tool
    - No unique configurable properties
    - Automatically creates Source Map variables related to the source channel if message is
       routed from Channel Writer:
          - sourceChannelId
          - sourceMessageId
    - If the Channel Reader receives a message from a channel in a chain, also creates Source
       Map variables containing all IDs for channels in the chain
          - sourceChannelIds
          - sourceMessageIds

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^335)
(^)


**NOTES**

### Channel Connectors

- Channel Writer:
    - Routes message to channel specified by ID
       - Select from drop-down list of existing channels to populate _Channel Id_
       - Alternatively use a Mapper variable for _Channel Id_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^336)


**NOTES**

### Channel Connectors

- Channel Writer (continued):
    - Legal to leave _Channel Id_ blank
       - Becomes “null” destination
    - Ability to send _Message Metadata_ to destination
       - Data other than the actual message
       - Based upon existing Mapper variable(s)
       - Any metadata variables added become Source Map variables for destination channel
    - Response Map variable:
       - Status Message: Text indicating channel routed successfully (or error), including ID of destination
          channel
       - Message: Message returned by destination channel (if that channel is set to return a response)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^337)
(^)


**NOTES**

### Channel Connectors

- **Note:** Destination channel does not need to be a channel with a Channel
    Reader
       - You can route to any channel, regardless of its source connector type

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^338)
(^)


**NOTES**

### Internal Routing

- **LAB 20:** Route messages between channels using Channel connectors
    - Create a channel group for the channels
    - Create “destination” channel with Channel Reader
       - Respond from auto-generated ACK
    - Create channel that receives message over TCP, routes to “destination” channel using
       Channel Writer
          - Channel Writer also sends IP address and port information as message metadata
    - Deploy channels, send message using HL7 Inspector
       _(continued next slide)_

Routing - Channel Writer (^) Routing - Channel Reader
HL7
Inspector (^6671) TCP Channel Channel
Listener Writer Reader
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^339)


**NOTES**

### Internal Routing

- **LAB 20** (continued)
    - Verify:
       - Message routed to destination channel as expected
       - Response from destination channel available as Response Map variable in source channel
       - Local address and port values from TCP Listener available as source map variables in destination
          channel

Routing - Channel Writer (^) Routing - Channel Reader
HL7
Inspector (^6671) TCP Channel Channel
Listener Writer Reader
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^340)


**NOTES**

# Batch Processing

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^341)
(^)


**NOTES**

## Batch Processing

- All source connectors (except DICOM) support processing batches of
    messages
       - Batches contain multiple messages in a single file or transmission
       - Processing a batch breaks it up into its individual messages
       - Example:
          - File Reader reads single HL7 batch file containing 50 messages. Channel processes each of the
             50 messages individually, in the order in which they appear in the batch file.

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^342)
(^)


**NOTES**

### Batch Processing

- Option to process the batch set in source connector’s Source Settings
- If batch processing disabled, the entire batch is treated as a single message
    (i.e., not broken up into its individual records/messages)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^343)
(^)
(^)
(^)
(^) Source Batch Settings


**NOTES**

### Batch Processing

- Example batches

```
Delimited Text (CSV)
```
```
HL7
```
```
XML
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^344)
<patientBatch>
**<patient>** <patientId>1001</patientId> (^)
<name><last>O'HALLAHAN</last> (^)
<first>COLLEEN</first>
</name>...^
**</patient>** ...^
**<patient>** <patientId>1234567</patientId> (^)
<name><last>Proctor</last> (^)
...<first>Morgan</first>
</name>
**</patient>** ...^
</patientBatch>...^
FHS|^~\&|SSYS|SAPP||NYSIIS|19990802091523||...
BHS|^~ **MSH** |^~\\&|SSYS&|SSYS (^) |SAPP|SAPP ||NYSIIS|19990802091524||ADT^A31...||NYSIIS|19990802091523||||... (^)
PID||45LR999|45LR999^^^^PI||JETSON^GEORGE^M^JR|...PD1|||||||||||02^REMINDER/RECALL^HL70215|Y| |...
NK1|2|JETSON^GEORGE|FTH^Father^HL70063
**MSH** PID||66782|66782^^^SR^~23LK729^^^^PI||PATIENT^MARIA|...|^~\&|SSYS|SAA||NYSIIS|19990802091524||VXU^04... (^)
PV1||R||||||||||||||||||V04^19990723|RXA|0|999|19990723|19990723|^^^90700^DTaP^CPT|0.5|||| (^)
RXA|0|999|19990723|19990723|^^^90707^MMR^CPT|0.5||||
**MSH** PID||927389|927389~92HG9257||SCHMOE^JOSEPH||^~\&|SSYS|SAPP||NYSIIS|19990802091526||VXU^04|...
PV1||R||||||||||||||||||V04^19990729|
RXA|0|999|19990729|19990729|^^^90707^MMR^CPT|0.5||||...BTS|3
FTS|1
**PatientID** ,LastName,FirstName,MiddleInit,DOB,Gender,Address1,Address2,City,State,PostalCode
**1234567890** ,Farnsworth,Hubert,J,19160920,M,18,Wong,Amy,,19810704,F,800 Mars St.,Apt. Elm Dr.,,New 8B,San YorkFrancisco,CA,90045 City,NY,01434 (^)
**1212124005** ,Fry,Philip,J,19730901,M,1602,Conrad,Hermes,,19640202,M,13 Washington Jamaica Place,,LakeBlvd.,Apt. 20J,Chicago,IL,45567 Forest,CA,92630
**88670** ,Kroker,Kif,,19780606,M,800 Mars St.,Apt. 8B,San Francisco,CA,90045
**22811** ,Leela,Turanga,,19700501,F,6620 Olympic Blvd.,Apt. 1I,New York City,NY,01433


**NOTES**

### Batch Processing

- Batch processing supported for all data types except DICOM
- Options for processing the batch (reading its individual records) in Set Data
    Types dialog

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^345)
Data Type-Specific
Batch Settings


**NOTES**

### Batch Processing

- Batch processing settings determine _how_ to break the batch into its individual
    messages
- All data types support writing custom JavaScript to get individual messages
    from batch
- HL7 v2.x, Delimited Text, and XML have other _Split Batch By_ settings specific to
    that data type
       - HL7 v2.x
          - MSH Segment
       - XML
          - Element Name, Level, XPath Query
       - Delimited Text
          - Record, Delimiter, Grouping Column

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^346)
(^)


**NOTES**

### Batch Processing

- For TCP Listener and File Reader, the batch data is streamed
- For all other source connectors, the entire batch is read into memory
- Only one response message will be returned to sending application per batch,
    regardless of the number of messages in the batch
       - Choose to respond when processing first or last message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^347)
(^)
(^)
(^)
(^)
(^) Batch Response Setting


**NOTES**

### Batch Processing

- Source Map variables automatically created for each message in the batch:
    - batchId – The message ID of the first message in the batch
    - batchSequenceId – The sequential position in the batch of the message
       - First message in the batch will always have ID 1
    - batchComplete – Boolean value (true/false) indicating if the message is the last message in
       the batch

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^348)
(^)


**NOTES**

### Batch Processing

- **Demo:** Process delimited text batch file
    - Channel with batch processing enabled
    - Reads Delimited Text (CSV) file with header row, six patient records
    - Inserts row into database table for each record in CSV file
    - Available as Supplemental Lab 30

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^349)
(^)


**NOTES**

### Batch Processing

- **LAB 21:** Process an XML batch file
    - Create channel with batch processing enabled
    - Channel reads XML batch file, splitting on <patient> tag
    - Process each patient record as an individual message
    - Write each message to file, using batchId and
       batchSequenceId source map variables in file name

```
/Training/outbox
```
```
/Training/inbox
*.xml
t
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^350)
Channel
File
Reader
XML
File Wri
er
<patientBatch>
**<patient>**
<patientId>1001</patientId>
<name>
<last>O'HALLAHAN</last>
<first>COLLEEN</first>
...
</name>
...
**</patient>
<patient>**
<patientId>1234567</patientId>
<name>
<last>Proctor</last>
<first>Morgan</first>
...
</name>
...
**</patient>**
...
</patientBatch>


**NOTES**

# Channel Configuration

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^351)
(^)


**NOTES**

### Destination Queues & Retries

- All destination connectors support queuing and retries
    - How to handle situation if destination is unreachable
    - If a connection to the destination cannot be established, message is written to queue (in
       Connect’s backend database), then background process will attempt to reconnect/resend
    - While destination is retrying (before queuing), message processing is held up
       - Subsequent destinations are waiting on the retrying destination
    - Once message is queued, message processing continues
       - Resend attempts happen asynchronously in background

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^352)
(^) Destination Queue/
Retry Settings
(^)


**NOTES**

### Destination Queues & Retries

- Queue options:
    - _Never_ – If unable to connect/send, message will be marked with a status of “ERROR”
       - Define number of retries, retry interval before error
    - _On Failure_ – Attempt to send first if queue is empty. If unable to send, put message in queue
       - Define number of retries, retry interval before queuing
    - _Always_ – Immediately put message in queue without attempting to send first
       - Subsequent destinations and Postprocessor won’t have access to response message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^353)
(^) Queue Messages
Settings
(^)


**NOTES**

### Destination Queues & Retries

- Advanced Queue Settings:
    - Click tool button to edit settings
    - _Retry Count Before Queue/Error_ – How many times to retry
       sending after the initial send attempt before placing the
       message in the queue (if _On Failure_ is selected) or marking the
       message with a status of “ERROR” (if _Never_ is selected)
    - _Retry Interval_ – How often to attempt to resend

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^354)
(^)
(^) Advanced Queue
Settings
(^)


**NOTES**

### Destination Queues & Retries

- Advanced Queue Settings (continued):
    - _Rotate Queue_ – If a send attempt fails, place message at end
       of queue
          - Prevents one bad message from blocking the queue
    - _Regenerate Template_ – Regenerate connector settings each
       time a send attempt is made
    - _Include Filter/Transformer_ – If _Regenerate Template_ is “Yes”,
       determines if the connector’s filter and transformer should be
       rerun

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^355)
(^)


**NOTES**

### Destination Queues & Retries

- Advanced Queue Settings (continued):
    - _Queue Threads_ – Number of threads that will attempt to
       process queued messages simultaneously
    - _Thread Assignment Variable_ – A Mapper variable used to
       determine by which thread the message is processed
          - Only used when _Queue Threads_ is greater than 1
          - All messages with the same variable value will be processed by the
             same thread
          - Maintains ordering for messages with that variable value
          - For example, Patient ID, MRN, etc.
    - _Queue Buffer Size_ – Maximum number of messages to be read
       into memory from the queue at a time

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^356)
(^)


**NOTES**

### Destination Queues & Retries

- Postprocessor script executes after all destinations have completed
    - If message has been queued, destination is considered completed
    - Will not execute again once message is finally sent
- Response transformer will not execute until message is finally sent from queue
    and a response is received from destination
- **Demo:** Using a destination queue

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^357)
(^)


**NOTES**

### Destination Chains

- For channels with multiple destinations, you can create destination “chains”
    - Each chain can be comprised of one or more destinations
    - Each separate chain runs concurrently
    - Destinations within a chain run sequentially
    - To create a new chain, uncheck the _Wait for previous destination_ box
    - Chain number listed in Chain column of destinations list table
    - Postprocessor script executes after all chains have completed processing
       - Regardless of if chains complete out-of-order
    - Channel Map variables defined in destinations are only in scope within the chain in which
       they are defined
          - Best practice: If using a Mapper variable in multiple destinations, define it in the source connector

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^358)
(^)


**NOTES**

### Deploy/Start Dependencies

- Channels can be configured to be dependent upon other channels
    - Channel won’t deploy/start until channels it depends upon are deployed/started
    - Channel with dependencies will undeploy/stop before channels it depends upon
- Examples:
    - A channel that routes to another channel
    - A channel that processes the output of another channel

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^359)
(^)


**NOTES**

### Deploy/Start Dependencies

- A channel can be dependent upon multiple channels
- A dependent channel can be a dependency for other channels
- Example:
    - A depends on B and C A
    - B depends on D
    - C depends on D and E
    - E depends on F
    - F does not depend on any channels

```
B C
```
```
D E
```
```
F
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^360)
(^)


**NOTES**

### Deploy/Start Dependencies

- Dependencies are set in the Channel
    Dependencies dialog
       - Click Set Dependencies button on channel’s
          Summary tab
       - Deploy/Start Dependencies tab
- Add channels that are dependencies for the
    channel, and/or channels that depend upon
    the channel
       - Cyclical references not allowed

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^361)
(^)


**NOTES**

### Deploy/Start Dependencies

- When deploying/starting a channel with dependencies, if dependent channels
    are not deployed/started, you will be prompted to include those channels in the
    deploy/start
       - Same for undeploying/stopping channels

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^362)
(^)


**NOTES**

### Deploy/Start Dependencies

- **Demo:** Defining deploy/start dependencies for three channels

```
A B C
```
- Verify channels deploy in order
    - C, then B, then A
- Verify channels undeploy in opposite order
    - A, then B, then C
- In each channel’s Deploy and Undeploy scripts:
    - Logging to indicate that the channel is deploying/undeploying
    - 3 - second sleep delay

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^363)
(^)


**NOTES**

# Mirth Connect Operations &

# Administration

```
Mirth Connect Fundamentals Training
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^364)
(^)


**NOTES**

### Logs and Logging

- All logging done via log4j2 logging utility
    - Versions prior to 4.1 use log4j
- log4j2’s logging level determines which logging statements should be logged
- Logging level indicates severity:
    - FATAL
    - ERROR
    - WARN
    - INFO
    - DEBUG
    - TRACE

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^365)
(^)


**NOTES**

### Logs and Logging

- Only logging done at a severity level at or above the configured level will
    appear in log
- Logging information written to mirth.log
    - Found in logs subfolder of installation folder
- Logging data also displayed on Server Log tab of Dashboard
    - Can be paused or cleared
- Logging information can come from Mirth Connect’s internal code (or any
    libraries it uses), or from any Mirth Connect JavaScript context

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^366)
(^)


**NOTES**

### Logs and Logging

- Instance of log4j2’s Logger available as global variable logger
- Call Logger’s corresponding method to log at a given logging level
    - Example:

logger.info("The value of x = " + x);

- logger.info() and logger.error() available in Reference list in Logging and Alerts
    category
       - fatal(), warn(), debug(), trace() also available

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^367)
(^)


**NOTES**

### Logs and Logging

- Log files can be viewed and logging level set on Server tab of Server Manager
- Three logging level settings:
    - Main – Overall logging level (rootLogger)
    - Database – Logging level for Java SQL-related classes
    - Channel – Logging level for JavaScript contexts within channels (transformer, preprocessor,
       etc.)
- Log files automatically rotated once configured max size is reached
    - Current log file backed up, new log file started
- Old log file backups automatically deleted once configured max backup count
    reached

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^368)
(^)


**NOTES**

### Logs and Logging

- For logging customization, edit log4j2.properties file
    - Found in conf subfolder of installation folder
    - Mirth Connect automatically edits this file when changing the logging levels in the Server
       Manager
    - For details on configuring log4j2:
       - https://logging.apache.org/log4j/2.x/manual/index.html
    - log4j2-cli.properties for CLI logging customization
- Filenames for Mirth Connect versions prior to 4.1:
    - log4j.properties
    - log4j-cli.properties

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^369)
(^)


**NOTES**

### User Management

- Mirth Connect allows for an unlimited number of
    user accounts
       - Managed from Users view
       - New users will see Welcome dialog first time logging in
- User log-in events and other actions audited in
    the Events browser

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^370)
(^)


**NOTES**

### User Management

- User passwords must conform to configured requirements
    - For example, minimum length, minimum number of numeric/special/uppercase/lowercase
       characters, etc.
    - Password requirements can be configured in conf/mirth.properties (or during installation)
- By default, all users have full administrator privileges

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^371)
# password requirements
password.minlength = 0
password.minupper = 0
password.minlower = 0
password.minnumeric = 0
password.minspecial = 0
password.retrylimit = 0
password.lockoutperiod = 0
password.expiration = 0
password.graceperiod = 0
password.reuseperiod = 0
password.reuselimit = 0


**NOTES**

### User Management

- Role-Based Access Control plug-in available to create user roles, define
    permissions
       - Available to Gold- and Platinum-level commercial license customers
       - Roles, privileges defined on User Authorization tab of Settings panel
          - Only displayed when plug-in is installed
       - Roles define privileges available for a user type
       - Each user can have multiple roles

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^372)
(^)


**NOTES**

### Events

- Events are actions performed by users, as well as some system actions
- Events are logged to backend database and can be viewed in the Events
    browser
- Events include:
    - User login/logouts, channel views/updates/ deployments/deletions/starts/stops, exceptions,
       message views, messages sent from Dashboard, settings views/updates, etc.
- If any Enterprise Extensions are installed, may also include events from those
    plugins
       - For example, downloading server certificates in SSL Manager

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^373)
(^)


**NOTES**

### Events

- Information displayed:
    - Date/time of event
    - Event name
    - Server ID
    - User who initiated event
    - Outcome
    - IP address from which
       event was initiated

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^374)
(^)


**NOTES**

### Events

- Event information
    - Server ID
       - The ID of the server where the event occurred
       - Only varies if multiple Connect servers running in a cluster (shared database)
    - Outcome
       - Red “X” indicates action failed
       - For example, failed login(wrong username/password) or attempt to install incorrect version of an
          extension

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^375)


**NOTES**

### Events

- Event details
    - For any event, click to display event details

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^376)


**NOTES**

### Events

- Events can be searched/filtered
    - Similar to Message browser
    - Click Advanced for Advanced Search Filter
- **Demo:** View events browser

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^377)


**NOTES**

### Settings

- Various Connect settings can be
    configured from Settings view
       - Divided into seven tabbed sections:
          - Server
          - Administrator
          - Tags
          - Configuration Map
          - Database Tasks
          - Resources
          - Data Pruner

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^378)
(^)


**NOTES**

### Settings

- Server settings – General:
    - _Environment name_
       - Name for all Connect servers
          sharing a single database via
          clustering
    - _Server name_
       - Name appears in title of Administrator window
       - If not specified, displays server URL
    - _Default Background Color_
       - Default background color for Administrator connecting to this server
       - Use different colors for different servers/environments (e.g., DEV, PROD, etc.)
       - Individual users can choose a different color for their Administrator
_(continued next slide)_

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^379)


**NOTES**

### Settings

- Server settings – General:
    - _Enable Auto Logout_
    - _Auto Logout Interval_
       - Automatically log out the current
          user after a specified period of
          inactivity
       - Closes the Administrator window, returns user to Login dialog
       - New feature in 4.0

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^380)


**NOTES**

### Settings

- Server settings – Channel:
    - _Clear global map on redeploy_
    - _Default Queue Buffer Size_
       - Default value for _Queue Buffer Size_ setting for source, destination queues
          - Each queue can be configured with a custom size
    - _Default Metadata Columns_
       - Source, Type, Version

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^381)


**NOTES**

### Settings

- Server settings – Email:
    - SMTP host settings
       - Used to relay alert emails
       - Similar to SMTP Sender settings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^382)


**NOTES**

### Settings

- Server settings – Notification:
    - _Require Login Notification and_
       _Consent_
          - If enabled, displays the given text
             upon login and requires the user to
             accept the terms before allowing access to the
             Administrator
    - _Login Notification_
       - Text to which the user must consent
    - New feature in 4.0

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^383)


**NOTES**

### Settings

- Server settings – Menu items:
    - Server Configuration Backup/Restore
    - Reset current and lifetime statistics for all channels

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^384)
(^)


**NOTES**

### Settings

- Administrator settings – System Preferences:
    - _Dashboard refresh interval_
       - Administrator queries server on each refresh
       - Can affect performance
    - _Message browser page size_
    - _Event browser page size_
    - _Format text in message browser_
       - Only applies to XML and JSON messages
    - Enable/disable dialogs/confirmations for:
       - _Message browser text search_
       - _Filter/Transformer Iterator_
       - _Message browser attachment type_
       - _Reprocess/remove messages_
    - Import/export code template libraries with channels

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^385)


**NOTES**

### Settings

- Administrator Settings
    - User Preferences
       - Check for notifications at login
       - Choose custom Administrator
          background color for user per
          environment
    - Code Editor Preferences
       - Auto-complete settings
       - Shortcut key mappings
    - **Note:** All System Preferences and Code Editor Preferences settings are client machine-
       specific, regardless of user or server
          - Only User Preferences setting is per-user

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^386)


**NOTES**

### Settings

- Database Tasks
    - Available tasks that can be run to optimize the backend database
    - Typically resulting from data migration due to a version update
    - Examples:
       - Deleting the old message table after updating from 2.x to 3.x
       - Deleting the old code templates table after updating to 3.3.x

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^387)


**NOTES**

### Alerts

- Alerts send notification emails when an exception is encountered during
    message processing
       - Send to multiple emails per alert
       - Specify email address or Connect user
       - Ability to send to all users with a specific role if Role-Based Access Control plug-in installed
- Alert data can also be forwarded to channels
    - Use channel to execute script, write to database, etc.
- Alert dashboard lists all configured alerts
    - Indicates count of times alert has been triggered
- Alert editor used to configure individual alerts

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^388)
(^)


**NOTES**

### Alerts

- Edit Alert view
    - Create/edit alerts

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^389)
(^)


**NOTES**

### Alerts

- Alert settings:
    - _Errors_ – Select in which parts of channel an error can trigger an alert
       - Source connector, destination connector, filter, transformer, preprocessor script, etc.
    - _Regex_ (optional)
       - Trigger alert if error/exception message contains a certain regular expression pattern
          - For example, “Connection refused”
       - Alert will not be triggered if Regex pattern not found

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^390)


**NOTES**

### Alerts

- Alerts are triggered by an
    exception in the channel
- An error message, with full
    stack trace, recorded for the
    exception
       - Stored with connector message
          - Viewable on Errors tab in Channel
             Messages view
       - Written to server log (mirth.log)
- Optional Regex is applied to
    this text

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^391)
TCP Sender error
ERROR MESSAGE: **Connection refused** : connect
java.net.ConnectException: **Connection refused** : connect
at java.net.DualStackPlainSocketImpl.waitForConnect(Native Method)
at java.net.DualStackPlainSocketImpl.socketConnect(Unknown Source)
at java.net.AbstractPlainSocketImpl.doConnect(Unknown Source)
at java.net.AbstractPlainSocketImpl.connectToAddress(Unknown Source)
at java.net.AbstractPlainSocketImpl.connect(Unknown Source)
at java.net.PlainSocketImpl.connect(Unknown Source)
at java.net.SocksSocketImpl.connect(Unknown Source)
at java.net.Socket.connect(Unknown Source)
at com.mirth.connect.connectors.tcp.SocketUtil.connectSocket(Socket...
at com.mirth.connect.connectors.tcp.TcpDispatcher.send(TcpDispatch...
at com.mirth.connect.donkey.server.channel.DestinationConnector.han...
at com.mirth.connect.donkey.server.channel.DestinationConnector.pro...
at com.mirth.connect.donkey.server.channel.DestinationChain.doCall...
at com.mirth.connect.donkey.server.channel.DestinationChain.call...
at com.mirth.connect.donkey.server.channel.Channel.process...
at com.mirth.connect.donkey.server.channel.Channel.dispatchRawMessa...
at com.mirth.connect.donkey.server.channel.SourceConnector.dispatch...
at com.mirth.connect.server.controllers.DonkeyEngineController....
at com.mirth.connect.server.api.servlets.MessageServlet.processMess...
at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
at java.lang.reflect.Method.invoke(Unknown Source)
at...


**NOTES**

### Alerts

- Alert settings:
    - _Channels_
       - Select which channel(s) can trigger the alert
          - Entire channel or individual connectors
          - Apply to any new channels, or new destinations within channels
    - _Actions_
       - Defines what action(s) to take when alert triggered
       - Email – Send to specified email address
       - User – Send to email address associated with user account
       - Channel – Forward template data to specified channel
       - Role – Send to all users with a given role
          - Only available if Role-Based Access Control plugin installed

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^392)


**NOTES**

### Alerts

- Alert settings:
    - _Subject_
       - Subject line for alert emails
    - _Template_
       - Email body if sent as email
       - Message content if forwarded to channel
    - _Alert Variables_
       - Predefined variables to use in _Subject_ , _Template_
       - See _Mirth Connect Programming Reference_ for description of variables
       - Can also use any Global Map variable
    - **Note:** If forwarding to a channel, data in _Template_ should either be formatted as a valid data
       type, or channel’s inbound data type should be set to Raw

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^393)


**NOTES**

### Alerts

- Alerts can also be programmatically triggered from any channel-level
    JavaScript context, as well as global Preprocessor and Postprocessor scripts
       - Not available in global Deploy or Undeploy
       - Example:

alerts.sendAlert("Alert message");

- Creates “User Defined Transformer” error
- String provided to sendAlert() will become the error message
    - Optionally use Regex to match to pattern in this string
- Will trigger any alerts for which the channel is enabled
- Available as code template “Trigger an Alert”
    - Logging and Alerts category

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^394)
(^)


**NOTES**

### Alerts

- Advanced Alerting plug-in available
    - Available to Gold-level commercial license customers
    - Features:
       - Event-based alerting (channel stop/start)
       - Metric-based channel monitoring
       - Threshold-based channel monitoring
       - Time-based performance monitoring
       - Alert scheduling
       - Escalation

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^395)
(^)


**NOTES**

### Alerts

- **Demo:** Creating, triggering an alert
    - Configure SMTP host
    - Create alert
       - Apply to channel with an TCP Sender
       - Trigger on Destination Connector error
       - Include some available variables in email body
    - Process message, verify receipt of alert email
    - Available as Supplemental Lab 32

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^396)
(^)


**NOTES**

### Extensions

- Extensions View
    - Manage all connectors and other plug-ins
    - Get latest extension updates
    - Disable/enable extensions
    - Install extensions from file system
    - Uninstall extensions

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^397)
(^)


**NOTES**

### Extensions

- Commercial license required for Enterprise Extensions
- License key must be added to mirth.properties
    - Entry does not exist by default
- Extensions can be downloaded from NextGen Success Community website
    - [http://community.nextgen.com](http://community.nextgen.com)
    - Search for “Mirth Connect Plug-In Central”
- **Demo:** Install new extensions, restart server, verify extensions available

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^398)
# license information
license.key = 9c1d30d3cb4e48eb78998f279192a1da-3aab94c23e633456f167a54...


**NOTES**

### Extensions

- Extensions available via commercial license
    - Silver Level
       - SSL Manager
       - Channel History
       - Message Generator
    - Gold Level
       - Advanced Alerting
       - Advanced Clustering
       - ASTM E1394 Data Type
       - ASTM E1381 Transmission Mode
       - Email Reader Connector
    - Platinum Level
       - Interoperability Connector Suite
          - FHIR Connector
          - LDAP Authentication
          - Multi-Factor Authentication (MFA)
          - Role-Based Access Control
          - Serial Connector

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^399)
(^)


**NOTES**

### Extensions

- Core Extension Bundle
    - Includes Silver-level extensions at lower price
       - Support not included

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^400)
(^)


**NOTES**

### Import/Export

- Several Connect components can be imported & exported:
    - Channels
    - Connectors
    - Transformers
    - Filters
    - Channel Groups
       - Global Scripts
       - Code Templates
       - Alerts
       - Messages
- Exports stored as XML files

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^401)
(^)


**NOTES**

### Import/Export

- Channel exports include all individual parts of the channel
    - Connectors, filters, transformers, message templates, channel scripts
       - Message templates are Base64-encoded, but not encrypted
- Export individual channels, selected channels, or all channels
    - Exporting multiple channels creates individual file for each channel
- Channels can be imported by dragging export files into Channels view (non-
    group mode only)
       - Allows importing multiple channels at once

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^402)
(^)


**NOTES**

### Import/Export

- Channels imported individually are added to the Default Group
- Exports of channel groups will include all channels within the group
- Importing a channel group maintains the channel/group relationship

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^403)
(^)


**NOTES**

### Import/Export

- Additional options for Message exports:
    - _Content_ – what message data to export
       - All message data serialized as XML, or just an individual message (raw, encoded, response, etc.)
       - XML serialized message is re-importable
       - Option to _Encrypt_ message data
       - Option to _Include Attachments_ if XML serialized message

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^404)
(^)


**NOTES**

### Import/Export

- Additional options for Message exports (continued):
    - _Compression_
       - None, zip, tar.gz, tar.bz2
    - _Password Protect_
       - Only available if exporting to zip file
    - _Export To_
       - Export to server or local computer

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^405)
(^)


**NOTES**

### Import/Export

- Additional options for Message exports (continued):
    - _File Pattern_
       - Variables available to dynamically name files
       - Unique variables such as Message ID can be used to generate individual files for each message
       - If compression is used, individual files are compressed into a single file (e.g., zip)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^406)
(^)


**NOTES**

### Server Configuration Backup

- The entire server configuration can be backed up/restored from the Settings
    view
       - From Server Tasks menu on Server tab
       - Configuration saved to XML file
       - Includes:
          - Channels
          - Channel Dependencies
          - Channel groups
          - Channel tags
          - Global Scripts
          - Alerts
             - Code templates/libraries
             - Server settings (on Server tab of
                Settings view)
             - Data Pruner settings
             - Resource settings
             - Configuration Map (added in 3.6)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^407)
(^)


**NOTES**

### Server Configuration Backup

- The intent of the server configuration backup is to make it easy to move all
    channels and related items from one server to another
       - For example, from development to production
       - Not a full backup of all data
       - Items not included in server config backup:
          - User accounts
          - Message data
          - Events
          - Administrator settings

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^408)
(^)


**NOTES**

### Data Pruning

- Both message data and events can be stored indefinitely, or automatically
    _pruned_ after a specified number of days
       - Deleted from the backend database
- Each channel has its own pruning settings
    - If to prune, how many days to keep messages, etc.
- Data Pruner is the process that performs the actual pruning

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^409)
(^)


**NOTES**

### Data Pruning

- Message pruning settings available on
    Summary tab for each channel
- _Prune older than_ settings for metadata,
    content
- Content can be pruned when metadata is
    pruned, or use a different days value
- Option to archive data before deleting
    - Archiving settings specified in Data Pruner
- Messages that are incomplete, have errors, or are queued will never be pruned

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^410)


**NOTES**

### Data Pruner

- Process that performs actual data deletion
- Settings view, Data Pruner tab
- Performs message removal across all
    channels
       - Deletes all messages older than a
          channel’s _Prune ... older than_ n _days_
          setting
       - Includes both deployed and non-deployed
          channels
- Can also prune event data
- Re-indexes database tables after removal

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^411)
(^)


**NOTES**

### Data Pruner

- Schedule
    - Data Pruner is not enabled by default
    - Uses same schedule settings as polling readers
       - Run on interval, at a time, or using Cron
       - _Prune now_ option for running data pruner at any time

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^412)


**NOTES**

### Data Pruner

- Prune Settings
    - Events can also be pruned when the data pruner runs
       - Deletes all events older than the specified age (days)
    - _Block Size_ defines max number of messages or events to delete in a single transaction

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^413)


**NOTES**

### Data Pruner

- Archive Settings
    - Option to archive message
       data before removal
    - Archives data to files
    - Same options as message
       exporter
          - _Archiver Block Size_ defines
             number of messages to cache
             while archiving
    - For messages to be archived for a given channel, archiving must be enabled in the Data
       Pruner and _Allow message archiving_ must be selected in the Message Pruning settings for
       that channel

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^414)


**NOTES**

### Data Pruner

- **Demo:** Configure Data Pruner, channel to prune message data
    - Update Rule Builder Filters channel to prune messages older than 1 day
    - Configure Data Pruner to run on a schedule, and archive message data to a file
    - Manually run Data Pruner using Prune Now
    - Verify message data has been archived, then deleted
    - Available as Supplemental Lab 34

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^415)
(^)


**NOTES**

### Backend Database

- Stores data for messages, channels, users, events, configuration, etc.
- Open-source version of Mirth Connect uses Apache Derby database
    - Performance decrease at about 100,000 messages
    - Not recommended for production use if storing message data

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^416)
(^)


**NOTES**

### Backend Database

- Mirth Connect can be configured to use other databases as its backend
    database
       - PostgreSQL, Oracle, MySQL, SQL Server officially supported
       - The Mirth Connect Server will automatically create database schema if it doesn’t exist
          - A database or schema to connect to should already be created, but can be empty
       - Back up server configuration before changing
       - Select database and set attributes using Server Manager
          - Or directly edit mirth.properties in conf folder
       - Data will remain on old database schema

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^417)
(^)


**NOTES**

### Backend Database

- **Demo:** Changing Mirth Connect’s backend database to PostgreSQL
    - Create server configuration backup
    - In Server Manager:
       - Change database type to postgres
       - Change URL to given database URL
       - Change Username, Password
       - Apply changes
       - Restart Connect Server
    - Start Administrator
    - Restore server configuration
- Available as Supplemental Lab 35

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^418)
(^)


**NOTES**

### Command Line Interface (CLI)

- Alternate user interface for Connect
- Interactive, scripted modes
- Ability to import/export channels, modify users, check channel stats and
    statuses, stop/start/pause/deploy channels, etc.
       - Cannot edit channels
- Communicates with server using the same REST interface as the Administrator
    (HTTPS)

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^419)
(^)


**NOTES**

### Command Line Interface (CLI)

- Run mccommand.exe in installation directory
    - Run mccommand on Mac or Linux
- Set properties for executing CLI in file conf/mirth-cli-config.properties, or on
    command line
- Required properties: address, username, password
    - Use – h command line option for usage info
- Once connected, displays server address and version, dollar sign command
    prompt
- Type help to list all available commands

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^420)
(^)


**NOTES**

### Command Line Interface (CLI)

- **LAB 22:** Launch CLI, walkthrough commands, list/start/stop channels

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^421)
(^)


**NOTES**

### Command Line Interface (CLI)

- Script mode allows a batch of commands to be executed
- Automatically disconnects when all commands completed
- Two ways to specify scripted mode and script file:
    - Add – s _scriptfile_ to command line:
       mccommand – s _scriptfile_
    - Add script= _scriptfile_ property to conf/mirth-cli-config.properties
- **Demo:** Running the CLI in script mode

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^422)
(^)


**NOTES**

### Mirth Connect Fundamentals Training Wrap-Up

- The remaining time is available for questions & answers on any Mirth Connect
    subject

Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^423)
(^)


**NOTES**

```
Confidential—For Use By Authorized Parties Only. Do Not Distribute.
```
(^)


**NOTES**

```
Property of NextGen Healthcare Information Systems, LLC and its parent company Quality Systems, Inc. (collectively "Company").
For Use By Authorized Parties Only.
NOTICE: This document contains information that is confidential and proprietary to Company and is intended for use solely by
authorized parties. This document may not be copied, reproduced, published, displayed, otherwise used, transmitted, or distributed in
any form by any means as a whole or in any part, nor may any of the information it contains be used or stored in any information
retrieval system or media, translated into another language, or otherwise made available or used by anyone other than the authorized
client to whom this document was originally delivered without the prior, written consent of Company.
By retaining or using this document, you represent that you a party who is authorized to use this document under one or more
agreements between you and Company now in force, and that you will use this document and the information it contains solely as and
to the extent such agreement(s) permit. If there is no agreement in place between the parties, you represent that you are the intended
recipient of this document and that you will at a minimum, hold any confidential or proprietary information it contains to the same
standards you would hold information from your own organization. Any other use or distribution of the contents of this document, as
a whole or in any part, is prohibited. Although we exercised great care in creating this publication, Company assumes no responsibility
for errors or omissions that may appear in this publication and reserves the right to change this publication at any time without notice.
Copyright © 2018 QSI Management, LLC. All Rights Reserved.
The registered trademarks listed at http://www.nextgen.com/legal-notice are the registered trademarks of QSI Management, LLC.
All other names and marks are the property of their respective owners.
Our issued and published patents can be found at http://www.nextgen.com/legal-notice.
```
Confidential—For Use By Authorized Parties Only. Do Not Distribute. (^425)
(^)


**NOTES**

1


**NOTES**

2


**NOTES**

3


**NOTES**

4


**NOTES**

5


**NOTES**

6


**NOTES**

7


**NOTES**

8


**NOTES**

9


**NOTES**

10


**NOTES**

11


**NOTES**

12


**NOTES**

13


**NOTES**

14


**NOTES**

15


**NOTES**

16


**NOTES**

17


**NOTES**

18


**NOTES**

19


**NOTES**

20


**NOTES**

21


**NOTES**

22


**NOTES**

23


**NOTES**

24


**NOTES**

25


**NOTES**

26


**NOTES**

27


**NOTES**

28


**NOTES**

29


**NOTES**

30


**NOTES**

31


**NOTES**

32


**NOTES**

33


**NOTES**

34


**NOTES**

35


**NOTES**

36


**NOTES**

37


**NOTES**

38


**NOTES**

39


**NOTES**

40
