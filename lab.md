

Mirth® Connect Fundamentals Training Lab Book, document version 4. (^1)
Copyright © 2025 NextGen Healthcare, Inc. All rights reserved.
This book is provided as part of the Mirth Connect Fundamentals Training or Mirth Connect Fundamentals
Certification Training class for the sole purpose of the attendee’s personal training use. It is not available for
sale or resale apart from attending one of the aforementioned training classes hosted by NextGen
Healthcare, Inc.
This document may not to be distributed, reproduced, transmitted, published or modified in any manor
without the express written permission of NextGen Healthcare, Inc.
All names, logos, images and marks appearing within these materials, except as otherwise noted, are
trademarks owned or used under license by NextGen Healthcare, Inc. The use or misuse of these
trademarks or any other content is prohibited.
The information in this book is to be used for training purposes only. Neither NextGen Healthcare, Inc. nor
the author of this book assume any responsibility for any errors or omissions, or for damages resulting from
the use of the information contained herein.
© 2009 - 2025 NextGen Healthcare, Inc.



## iii nextgen.com

**Contents**


- Lab 1 Start/Stop Mirth Connect Server In-Class Labs
- Lab 2 Launch the Mirth Connect Administrator Using Administrator Launcher
- Lab 3 Create and Deploy a Simple Channel
- Lab 4 Create Filters using Rule Builder
- Lab 5 Create Plain Text Patient Report Using Mapper Transformer Steps
- Lab 6 Create XML Message Using Message Builder Transformer Steps
- Lab 7 Modify Values in a Message Using Message Builder Transformer Steps
- Lab 8 Create and Populate a Channel Group
- Lab 9 Receive, Send Messages Using TCP Connectors in MLLP Transmission Mode
- Lab 10 Create a Channel that Reads a File from a Local Folder and Writes to an SFTP Server
- Lab 11 Generate HL7 Messages from Rows in a Database Table
- Lab 12 Extract Data from Inbound HL7 Messages, Write Data to Database
- Lab 13 Generate a Patient Report PDF Document Using the Document Writer
- Lab 14 Create and Use Configuration Map Variables
- Lab 15 Use Iterator Transformer to Build New Message with Repeating Data
- Lab 16 Use Iterator Filter to Accept Messages with Condition in Repeating Segment
- Lab 17 Use a JavaScript Transformer to Iterate over Repeating Segments and Build Lab Report
- Lab 18 Use a JavaScript Transformer to Iterate over Repeating Segments and Modify the Message
- Lab 19 Use Response Transformers to Process an HL7 Patient Query Response
- Lab 20 Create Channels that Route Messages Using Channel Connectors
- Lab 21 Process an XML Batch File
- Lab 22 Launch Command Line Interface, Execute Commands
- Lab 23 Add Custom Formatting to HL7 Data in Mappers Supplemental Labs
- Lab 24 Install a New Database Driver for Use with the Database Reader/Writer Connectors
- Lab 25 Send Email with PDF Attachment Using SMTP Sender
- Lab 26 Use JavaScript Filter for Value in Repeating Segment
- Lab 27 Create Global Deploy Script to Load Translation Table from Database
- Lab 28 Use a Postprocessor Script to Generate an ACK from a Destination that Uses Queuing
- Lab 29 Modify a Destination’s Response Using Response Transformers
- Lab 30 Process a CSV Batch, Write Results to Database iv nextgen.com
- Lab 31 Create a CSV Batch File from HL7 Messages
- Lab 32 Create, Trigger an Alert
- Lab 33 Programmatically Trigger an Alert, Forward Alert Data to a Channel
- Lab 34 Configure Data Pruner, Channel for Message Pruning
- Lab 35 Change the Backend Database to PostgreSQL
- Lab 36 Create a Script File and Run the Command Line Interface in Script Mode
- Lab 37 Launch the Mirth Connect Administrator Using Java Web Start
- Lab 38 Manually Parse an HL7 Message
- Application A HL7 Inspector Using the Third-Party Applications


```
nextgen.com
```
Section One

In-Class Labs

© 2009 - 2025 NextGen Healthcare, Inc.



```
3 nextgen.com
```
## Lab 1 Start/Stop Mirth Connect Server

**Objectives**
In this lab, you will start and stop the Mirth Connect Server, using three different methods: the Server
Manager, the mcservice executable from the command line, and the Windows Services Console. The
Connect Server should already be running as a service on your computer.

**Estimated Time to Complete**
5 minutes

**Tools Used**

- Server Manager
- Windows Command Prompt

**Step-By-Step**

1. Open the Server Manager by double-clicking its icon in the Windows notification area (system tray).
    This is the icon indicated in Figure 2-1, below. If you do not see the icon in the notification area, the
    Server Manager may not be running. To start it, select All Programs > Mirth Connect > Mirth Connect
    Server Manager from the Windows Start menu.

```
Figure 1 - 1 Server Manager Icon in Notification Area
```
2. The Server Manager should show that the service is currently running (by the fact that the Start button is
    disabled). Click the Stop button to stop the server.

```
Figure 1 - 2 Server Manager - Service Tab
```

```
4 nextgen.com
```
3. After a few seconds, you should notice that the Server Manager logo is now “greyed-out”, and a
    notification window should appear indicating that the service was successfully stopped. Click OK
4. Open a Command Prompt window by clicking the Command Prompt icon in the Taskbar (or select All
    Programs > Accessories > Command Prompt from the Windows Start menu)

```
Figure 1 - 3 Command Prompt in Windows Taskbar
```
5. At the command prompt, change to the installation directory for Connect (usually “\Program Files\Mirth
    Connect”). For example:
    cd "\Program Files\Mirth Connect"
    **Note:** This step is only necessary if you are doing the lab in your own environment. The PC supplied for
    your training class is already configured to open directly into the correct installation directory.
6. Start the Connect Server from the command line by typing mcservice /start at the command
    prompt and pressing Enter. This will begin the startup process. You can now double-click the Server
    Manager icon once again (or click the Refresh button on the Service tab of the Server Manager) to
    update its status and see that the service is once again running.
7. Check the status of the Connect Server from the command line (optional). At the command prompt,
    type mcservice /status and press Enter. This should display the following two lines:
    Running.
    Auto-start.
8. To stop the Connect Server from the command line, type mcservice /stop at the command prompt
    and press Enter. Within a few seconds, you should see a message in the Command Prompt window
    indicating that the service has been stopped. You can now once again double-click the Server Manager
    icon once again (or click the Refresh button on the Service tab of the Server Manager) to update its
    status and see that the service is stopped.
9. Once again check the status of the Connect Server from the command line (optional). At the command
    prompt, type mcservice /status and press Enter. This should display the following two lines:
    Not running.
    Auto-start.
10. Open the Windows Services console by clicking the Services icon in the Taskbar (or select All Programs
    > Administrative Tools > Services from the Windows Start menu)

```
Figure 1 - 4 Services Console in Windows Taskbar
```
11. In the Services console, scroll down until you find Mirth Connect Service, and select it (Figure 1 - 5 )


```
5 nextgen.com
```
12. In the Services console window, click the link on the left-hand side to Start the service. You can also
    start the service by right-clicking on Mirth Connect Service and selecting Start from the context menu.
    Within a few seconds, you should see “Started” in the Status column of the Services console for Mirth
    Connect Service.

```
Figure 1 - 5 Windows Services Console
```
13. Double-click the Server Manager icon once again to update its status and see that the service is once
    again running.

**Results**
After completing each of the above steps, the Mirth Connect Server should be actively running as a service.


```
6 nextgen.com
```
## Lab 2 Launch the Mirth Connect Administrator Using Administrator Launcher

**Objectives**
In this lab, you will launch the Mirth Connect Administrator using the Mirth Connect Administrator Launcher.
In the Administrator Launcher, you will create and save a new connection to the local Mirth Connect Server
instance, and then launch the Administrator to connect to that server. If this is your first attempt to login to
the Administrator, you will also need to customize the default user information after logging in.

**Estimated Time to Complete**
3 - 4 minutes.

**Tools Used**

- Administrator Launcher
- Connect Administrator

**Step-By-Step**

1. Open the Administrator Launcher, and configure a connection to the local Mirth Connect Server
    a. Find the shortcut for the Mirth Connect Administrator Launcher on your desktop (Figure 2 - 1 ) and
       double-click it to open. Alternatively, you can select All Programs > Mirth Connect Administrator
       Launcher, Mirth Connect Administrator Launcher from the Windows Start menu.

```
Figure 2 - 1 Administrator Launch Icon on Desktop
```
```
b. In the Administrator Launcher, the Address field is pre-populated with the correct URL for connecting
to the local Connect Server on your computer (Figure 2 - 2 ). Click Save As... to save these settings
as a connection.
```

```
7 nextgen.com
```
```
Figure 2 - 2 Administrator Launcher (No Saved Connections)
```
c. A dialog will appear prompting you to enter a name for the connection (Figure 2 - 3 ). Replace the
default name with Local Connect Server (or any other name you choose) and click OK.

```
Figure 2 - 3 New Connection Name Dialog
```
d. You should now see the connection displayed in the Connections list (Figure 2 - 4 )


```
8 nextgen.com
```
```
Figure 2 - 4 Administrator Launcher with Saved Connection
```
```
e. Click the Launch button to the right of the Address field to launch the Administrator
```
2. Once the Login dialog appears (Figure 2 - 5 ), provide the default credentials for logging into the
    Administrator

```
Figure 2 - 5 Connect Login
```
```
a. For the Server field, leave the default address: https://localhost:
b. For the Username field, type admin
c. For the Password field, type admin
d. Click the Login button
```
3. In the Welcome to Mirth Connect dialog (Figure 2 - 6 ), customize the default user information by entering
    information in each of the required fields (marked with a red asterisk). Note that you can keep the
    default username and password as admin/admin by re-entering those values in the corresponding fields,
    or you can enter a different username and password to overwrite admin/admin.


```
9 nextgen.com
```
**Note:** Your training WorkSpace may be configured so that this step has already been completed. If so,
you will not see this dialog, and you can skip to Step 4.

```
Figure 2 - 6 Welcome to Mirth Connect
```
a. In the Username field, type admin to keep the username as admin, or type a new username to
change it
b. In the Password field, type admin to keep the password as admin, or type a new password to
change it
c. In the Confirm Password field, re-type the same password that you entered in the Password field
d. Note your username and password for future reference (optional)

```
Username:
```
```
Password:
```
e. Uncheck the box for “I consent to receive email updated and marketing messages from NextGen
Healthcare”
f. Enter your information into the First Name, Last Name, Email, Country, and Organization fields
g. Click the Finish button


```
10 nextgen.com
```
4. Next, the Notifications dialog will display (Figure 2 - 7 ), showing any news or important information about
    Connect.

```
Figure 2 - 7 Notifications
```
```
a. Remove the check for the Show new notifications on login check box
b. Click the Close button
```
**Results**
You should now be logged into the Administrator. If you view the Users list by clicking Users in the Mirth
Connect menu (top, left-hand side of the Administrator window), you should see a single user with the
information entered in the Welcome dialog.


```
11 nextgen.com
```
## Lab 3 Create and Deploy a Simple Channel

**Objectives**
In this lab, you will:

- Create a simple “pass-through” channel using the TCP Listener (in MLLP transmission mode) as the
    source connector, and the File Writer as the destination connector, using the default connector
    settings whenever possible. The channel will receive messages over the MLLP protocol, and simply
    write out any messages received to a file.
- Save and deploy the channel
- Send a test message using HL7 Inspector
- Verify the results in both the Dashboard and Channel Messages views, as well as in the HL
    Inspector

```
Figure 3 - 1 MLLP to File Channel Flow
```
**Estimated Time to Complete**
10 - 15 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer

**Step-By-Step**

1. Create a new channel in the Default Group
    a. In the Mirth Connect menu, click Channels to switch to Channels view
    b. In the Channel Tasks menu, click New Channel
2. Set the channel’s Summary tab properties
    a. In the Channel Name field, type a name for the channel (for example, _Simple Channel - MLLP to_
       _File_ ). Note that only alphanumeric, space, hyphen and underscore characters are allowed
    b. Leave all other settings on the Summary tab as their defaults
3. Set the source connector properties
    a. Click the Source tab near the top of the Channel view to display the source connector properties
    b. In the Connector Type drop-down list, select TCP Listener
    c. Leave all other settings as their defaults


```
12 nextgen.com
```
```
d. In the Listener Settings section, note the default Local Port value of 6661 (but do not change it).
This will be used to configure the HL7 Inspector to send to the channel.
```
4. Set the destination connector properties
    a. Click the Destinations tab near the top of the Channel view to display the destination connector
       properties
    b. Rename the default destination connector
       i. In the destinations list at the top of the Destinations page, double-click the cell that displays
          “Destination 1” to make it editable
ii. Select the existing text (“Destination 1”) and delete it
iii. Type a new name for the destination (for example, Output File)
iv. Press the Enter key to save the change
    c. In the Connector Type drop-down list, select File Writer
    d. In the Directory field of the File Writer Settings section, type /Training/outbox
    e. Define the output file name as a unique ID followed by a .txt extension
       i. From the Destination Mappings box to the right, drag-and-drop the Unique ID mapping into
          the File Name field by clicking Unique ID, and while holding down the left mouse button, drag
          the mouse cursor to the File Name field then release the mouse button. This inserts the
          ${UUID} placeholder.
ii. After the ${UUID} placeholder, type .txt
**Note:** The ${UUID} placeholder remains selected after dragging over. To avoid typing over
it, you will need to either press the right arrow key or click with your mouse after the
placeholder to deselect it.
The value in the File Name field should now be:
${UUID}.txt
    f. For the Template field, drag-and-drop the Encoded Data destination mapping using the same
       method as the Unique ID mapping in the previous step. The value in the Template field should now
       be:
       ${message.encodedData}
5. Save the channel
    a. Click Save Changes in the Channel Tasks menu
6. Deploy the channel
    a. Click Deploy Channel in the Channel Tasks menu. This will display a dialog prompting for
       confirmation of the deployment (Figure 3 - 2 )

```
Figure 3 - 2 Deployment Confirmation
```
```
b. Click the Yes button to continue with the deployment. Within a few seconds, you should see your
channel appear in the Administrator’s Dashboard view
```

```
13 nextgen.com
```
7. Send a message using HL7 Inspector
    a. Open HL7 Inspector by clicking the HL7 Inspector icon in the Taskbar (Figure 3 - 3 ). Alternatively,
       you could open HL7 Inspector by selecting All Programs > HL7 Inspector > HL7 Inspector from the
       Windows Start menu.

```
Figure 3 - 3 HL7 Inspector in the Windows Taskbar
```
```
b. Open HL7 Inspector’s Message Sender pane by clicking the Send Selected Messages toolbar
button. This is the button with the red, upward-pointing arrow (Figure 3 - 4 )
```
```
Figure 3 - 4 Button to Open HL7 Inspector's Message Sender
```
```
c. In the Message Sender tab, click the button with the screwdriver and wrench in the toolbar for the
Message Sender pane to open the Send Options dialog (Figure 3 - 5 )
```
```
Figure 3 - 5 HL7 Inspector Setup Sender Options Button
```
```
d. In the Host/Port field of the Send Options dialog, replace the default port value of 2100 with 6661
(the default port for the TCP Listener connector) (Figure 3 - 6 )
```

```
14 nextgen.com
```
```
Figure 3 - 6 HL7 Inspector Send Options
```
e. Click OK
f. Open a file to send by selecting File Open... from the File menu and browsing to one of the HL7 files
in the “\Training\Messages\HL7” folder
g. Upon selecting the file to open, HL7 Inspector will display the Import Options dialog (Figure 3 - 7 ). Do
not change any of the settings in this dialog; simply click the OK button

```
Figure 3 - 7 Import Options
```
h. Click the message in the message tree (in the top pane of the HL7 Inspector window) to select it
i. In the Message Sender pane, click the Send button (blue triangle) to send the message


```
15 nextgen.com
```
**Results**
To verify the message was sent correctly, you should now see the following results:

- HL7 Inspector received an ACK message in response to the message sent
- The statistics displayed for the channel in the Administrator’s Dashboard should show one message
    received and one message sent
- The Channel Messages view for the channel (click the channel in the Dashboard, then click View
    Messages from the Dashboard Tasks menu) should show two rows bound to a single message ID:
    one for the source connector and one for the destination connector. The status for the source
    connector should be TRANSFORMED, while the status for the destination connector should be
    SENT.
- In the “/Training/outbox” folder, you should see a file with a name consisting of a unique ID followed
    by a .txt extension. The contents of this file should be the HL7 message sent by HL7 Inspector.


```
16 nextgen.com
```
## Lab 4 Create Filters using Rule Builder

**Objectives**
In this lab, you will create a new channel to demonstrate the use of filters with Rule Builder rules to not only
filter out unwanted messages, but to route messages to different destinations based on data from the
message. The channel will have a TCP Listener source connector (in MLLP transmission mode) and two
File Writer destination connectors. Rule Builder filter rules will be added to the source connector to filter out
any messages that are not ADT messages, as well as any messages that are not being sent from “Hospital
A” or “Hospital B”.

Each File Writer destination connector will write to a different folder based on the sending facility, using Rule
Builder filter rules to route the message to the correct folder by filtering out (rejecting) messages where the
sending facility does not correspond to the folder to which to write.

**Figure 4 - 1 Filters Channel Flow**

**Estimated Time to Complete**
20 - 25 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer

**Step-By-Step**

1. Create a new channel in the Default Group named _Rule Builder Filters_
2. Configure the source connector as a TCP Listener in MLLP transmission mode
    a. Click the Source tab to view the source connector settings
    b. From the Connector Type drop-down list, select TCP Listener
    c. In the Listener Settings section, change to Local Port value to 6662
       **Note:** Changing the Local Port value is necessary because the default Local Port value (6661) is
       already in use by the channel created in Lab 3.
3. Define an inbound message template for the source connector
    a. In the Channel Tasks menu, click Edit Filter


```
17 nextgen.com
```
```
b. In the right-hand pane of the window, click the Message Templates tab
c. Click the Open File button (Figure 4 - 2 )
```
```
Figure 4 - 2 Open File Button for Inbound Message Template
```
```
d. Browse to and open any ADT message file in the “\Training\Messages\HL7” folder
```
4. Create a filter rule for only accepting messages with a sending facility value of “Hospital A” or “Hospital
    B”
    a. Click the Message Trees tab (to the immediate left of the Message Templates tab) to view the
       Inbound Message Template Tree
    b. In the Filter field, type sending facility and press Enter
    c. The tree should now only be displaying the branch for MSH.4.1 (Sending Facility). Look for the
       lower-most node on the tree, indicated by a green dot next to the sample value, and situated below
       the “MSH.4.1” branch
    d. Select this node with your mouse and drag and drop it into the filter rule list area at the top center
       part of the window (Figure 4 - 3 )

```
Figure 4 - 3 Dragging-and-Dropping from Inbound Message Template Tree
```
```
e. A dialog will appear asking if you would like to add the filter rule to an Iterator (Figure 4 - 4 ). Tick the
box labeled “Do not show this dialog again...” and then click No
```
```
Figure 4 - 4 Add Filter Rule to Iterator Dialog
```

```
18 nextgen.com
```
```
f. In the rule detail area (below the filter rules list), edit the code in the Field property so that it looks
like the following (the bolded part is the code to add):
msg['MSH']['MSH.4']['MSH.4.1'].toString() .toUpperCase()
Note: You must type the code exactly as indicated, including case
g. Select the Equals radio button
h. Click the New button to add a new value to the Values list
i. Double-click the value cell to make it editable
j. Type "HOSPITAL A" (quotes included) and press Enter
k. Click the New button again to add a second value to the Values list
l. Double-click the new value cell to make it editable
m. Type "HOSPITAL B" (quotes included) and press Enter
n. The rule should now look like Figure 4 - 5 (below)
```
```
Figure 4 - 5 Source Filter Rule for Sending Facility
```
5. Create a filter rule for only accepting messages of type “ADT”
    a. In the Filter field of the Messages Tree tab, type message type and press Enter
    b. The tree should now only be displaying the branch for MSH.9 (Message Type), which includes two
       sub-branches, MSH.9.1 (Message Type), and MSH.9.2 (Trigger Event). Select the node below
       MSH.9.1 and drag and drop it into the filter rules list
    c. Click the Equals radio button
    d. Click the New button to add a new value to the Values list
    e. Double-click the value cell to make it editable
    f. Type "ADT" (quotes included) and press Enter
    g. The rule should now look like Figure 4 - 6 (below)

```
Figure 4 - 6 Source Filter Rule for Message Type
```

```
19 nextgen.com
```
```
h. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel view
```
6. Configure the default destination as a File Writer for “Hospital A”
    a. Click the Destinations tab to view the channel’s destination connectors
    b. Rename the default destination from “Destination 1” to “Hospital A”
    c. In the Connector Type drop-down list, select File Writer
    d. In the Directory field of the File Writer Settings, type /Training/outbox/Hospital A
       **Note:** The “Hospital A” subfolder of the “outbox” folder does not currently exist. Therefore, if you
       click the Test Write button, you will get a warning message indicating that you are unable to connect.
       Once you deploy and test the channel, the File Writer will automatically create the folder path for
       you.
    e. Define the output file name as a unique ID followed by a .txt extension, as was done in Lab 3
    f. In the Template field, set the output to the message encoded data by dragging-and-dropping the
       Encoded Data mapping from the Destination Mappings box
7. Define an inbound message template for the Hospital A destination connector (this is the same as was
    done in Step 3 )
    a. In the Channel Tasks menu, click Edit Filter
    b. In the right-hand pane of the window, click the Message Templates tab
    c. Click the Open File button (the button with file and magnifying glass)
    d. Browse to and open any ADT message in the “\Training\Messages\HL7” folder
8. Add a filter rule to the Hospital A destination connector to only accept messages with a sending facility
    value of “HOSPITAL A”
    a. Click the Message Trees tab to view the Inbound Message Template Tree
    b. In the Filter field, type sending facility and press Enter
    c. The tree should now only be displaying the branch for MSH.4.1 (Sending Facility). Look for the
       lower-most node on the tree, indicated by a green dot, and situated below the “MSH.4.1” branch
    d. Select this node with your mouse and drag and drop it into the filter rule list area at the top center
       part of the window
    e. In the rule detail area (below the filter rules list), edit the code in the Field property so that it looks
       like the following (the bolded part is the code to add):
       msg['MSH']['MSH.4']['MSH.4.1'].toString() **.toUpperCase()**
    f. Select the Equals radio button
    g. Click the New button to add a new value to the Values list
    h. Double-click the value cell to make it editable
    i. Type "HOSPITAL A" (quotes included) and press Enter
    j. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel view
9. Create a second File Writer destination that will write to a file only messages that have a sending facility
    value of “HOSPITAL B”. Because the connector settings and filter rules for this destination will be
    identical to those of the first destination, you can just clone the first destination and change all instances
    of “HOSPITAL A” to “HOSPITAL B”
    a. In the Channel Tasks menu, click Clone Destination
    b. When prompted to save your channel before cloning the destination, click Yes
    c. Select the new destination, “Destination 1” in the destinations list
    d. Rename the destination to “Hospital B”
    e. In the Directory field, change the destination folder to:
       /Training/outbox/Hospital B


```
20 nextgen.com
```
```
f. Click Edit Filters in the Channel Tasks menu
g. Double-click the value cell containing "HOSPITAL A", change it to "HOSPITAL B" and press Enter
to accept the change
h. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel View
```
10. Save the channel
11. Deploy the channel
12. Test the channel using HL7 Inspector
    a. In HL7 Inspector, change the port to which to send to the Local Port value in your channel’s TCP
       Listener (6662). Click the “Setup sender options” button (Figure 4 - 7 ) to change this setting

```
Figure 4 - 7 HL7 Inspector Setup Sender Options Button
```
```
b. Optional: If you would like to clear out the messages imported into HL7 Inspector in the previous
lab, you can remove all loaded messages by clicking the broom button in the toolbar above the
messages tree (Figure 4 - 8 ). Likewise, you can also clear the trace log in the Message Sender tab of
HL7 Inspector by clicking the broom button in its toolbar (Figure 4 - 9 ).
```
```
Figure 4 - 8 HL7 Inspector’s Clear Tree Button
```
```
Figure 4 - 9 HL7 Inspector's Clear Trace Log Button
```

```
21 nextgen.com
```
```
c. Open the following message files (found in “\Training\Message\HL7”) in HL7 Inspector (you will need
to open them one-at-a-time):
```
- ADT-A0 3 - Hermes Conrad - Hospital A.hl7
- ADT-A08 - John Panucci - Sacred Heart.hl7
- ADT-A08 - Lars Fillmore - Hospital B.hl7
- ORM-O01 - Ogden Wernstrom - Hospital B.hl7
- ORU-R01 - Hermes Conrad - Hospital A.hl7
d. Select all the imported messages by clicking the first one, holding down the Shift key, and clicking
the last one, as shown in Figure 4 - 10 (below)

```
Figure 4 - 10 HL7 Inspector with Five Messages Selected to Send
```
```
e. Click the blue “Send selected messages” button to send all of the selected messages to the channel
```
**Results**
The statistics for the entire channel in the dashboard should display the following counts: 5 Received, 5
Filtered, and 2 Sent. If you expand the channel to view the statistics for each individual connector, you
should see the following statistics:

- Source: 5 Received, 3 Filtered, and 0 Sent
- Hospital A: 2 Received, 1 Filtered, and 1 Sent
- Hospital B: 2 Received, 1 Filtered, and 1 Sent

These statistics indicate that for the five messages sent to the source connector, three of them were filtered.
From this, we can deduce two messages were accepted by the source connector’s filter, and passed onto
each of the destination connectors.

For the two messages that were accepted by the source connector, each was filtered by _one_ of the
destination connectors. In other words, both destinations accepted one of the two messages (the one that
matched its sending facility filter), and filtered the other.

The following table shows the source connector filter status and reason for each of the five messages sent:


```
22 nextgen.com
```
```
Message File Name Source
Connector
Reject/Accept
```
```
Reject/Accept Reason
```
```
ADT-A0 3 - Hermes Conrad - Hospital A.hl7 Accepted Both message type (ADT) and
sending facility (Hospital A)
requirements met
ADT-A08 - John Panucci - Sacred Heart.hl7 Rejected Sending facility (Sacred Heart)
requirement not met
ADT-A08 - Lars Fillmore - Hospital B.hl7 Accepted Both message type (ADT) and
sending facility (Hospital B)
requirements met
ORM-O01 - Ogden Wernstrom - Hospital B.hl7 Rejected Message type (ORM)
requirement not met
ORU-R01 - Hermes Conrad - Hospital A.hl7 Rejected Message type (ORU)
requirement not met
```
**Table 4 - 1 Accepted/Rejected Statuses for Messages Sent**

For the three messages that were filtered by the source connector, in the HL7 Inspector you should see the
ACK message received with an acknowledgement code of AR (application reject). Likewise, for the two that
were successfully received and sent by one of the destination connectors, you should see the ACK message
with an acknowledgement code of AA (application accept).

In the Channel Messages view for the channel, you should see a status of FILTERED in the Source
connector row for the three messages rejected by the source connector. For the two messages accepted by
the source connector, you should see a status of TRANSFORMED in that row. For the two destination
connector rows, you should see one with a status of SENT and the other with a status of FILTERED,
depending upon the value of the MSH.4.1 (Sending Facility) component.

Finally, in the “/Training/outbox” folder, you should now see two new folders, “Hospital A” and “Hospital B”.
Each folder should contain one file, with the contents of each file being the message with the Sending
Facility value corresponding to the folder in which it was written.


```
23 nextgen.com
```
## Lab 5 Create Plain Text Patient Report Using Mapper Transformer Steps

**Objectives**
In this lab, you will create a new channel to demonstrate the use of Mapper transformer steps to extract data
from the inbound message for use in the destination connector. The channel will have a TCP Listener
source connector and a File Writer destination connector. In the transformer for the File Writer, you will use
Mapper steps to extract patient demographic data from the inbound message using drag-and-drop. Then,
you will use the Mapper variables in the File Writer’s template to populate the text report with the patient
data and write the resulting report to a file.

**Figure 5 - 1 Transformers - Create Text Report Channel Flow**

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Create a new channel in the Default Group named _Transformers – Create Text Report_
2. Configure the source connector as a TCP Listener (in MLLP transmission mode)
    a. Select TCP Listener from the Connector Type drop-down list
    b. In the Listener Settings section, change the Local Port value to 6663
3. On the Destination tab, configure the default destination as a File Writer that will generate a patient
    report text file
    a. Rename the destination to Patient Report File
    b. Change the Connector Type to File Writer
    c. In the Directory field of the File Writer Settings section, type /Training/outbox
    d. Leave the File Name field blank for now
    e. In the Template field, type the following text, with a space character at the end of each line ( **Note:**
       This text can also be copied from the file “Text Patient Report Template.txt” in the
       “/Training/Miscellaneous” folder):


```
24 nextgen.com
```
```
Patient Report - Created
-----------------------------------
Patient ID:
Last Name:
First Name:
Middle Name:
Date of Birth:
Gender:
```
4. Create the Mapper transformer steps to extract the required patient data from the message
    a. Click Edit Transformer in the Channel Tasks menu
    b. Set the Inbound Message Template on the Message Templates tab to any HL7 ADT message
    c. Click the Message Trees tab to view the Inbound Message Template Tree
    d. In the Inbound Message Template Tree, find the PID segment (patient identification), and expand it
       by clicking the “+” to the left of it

```
Figure 5 - 2 Creating a Mapper Transformer Using Drag-and-Drop
```
```
e. For each of the entries below in Table 5 - 1 , repeat the following steps, i through iv
i. Under the PID branch of the tree, find the field listed in the “HL7 Field” column of Table 5 - 1
on page 25. If the branch for that field is not already expanded in the tree, expand it by
clicking the “+” so that its contents are visible
ii. Under the field branch of the tree, find the component listed in the “HL7 Component” column
of Table 5 - 1. Expand its branch by clicking the “+”. You should now see the component’s
sample data next to a green dot
iii. Click in the sample data next to the green dot, and while holding down the left mouse button,
drag and drop the value into the transformer steps list as shown above in Figure 5 - 2 (release
the mouse button to drop). This will create a new mapper variable with a default variable
name
iv. In the Variable field, rename the variable to the value listed in the “Rename Variable To”
column of Table 5 - 1
```

```
25 nextgen.com
```
```
HL7 Field HL7 Component Rename Variable To
PID.2 PID.2.1 patientId
PID.5 PID.5.1 lastName
PID.5 PID.5.2 firstName
PID.5 PID.5.3 middleName
PID.7 PID.7.1 dateOfBirth
PID.8 PID.8.1 gender
Table 5 - 1 Mappings from HL7 Message to Mapper Variables
```
```
f. Click Back to Channel from the Mirth Connect Views menu
```
5. Finish configuring the Patient Report File Writer destination connector
    a. Set the File Name field to a combination of the patient ID and message ID, followed by a .txt
       extension
          i. Drag-and-drop the patientId mapping from the Destination Mappings list to the File Name
             field
ii. After the ${patientId} placeholder, type an underscore: _
iii. After the underscore, drag-and-drop the Message ID mapping from the Destination
Mappings list
iv. After the ${message.messageId} placeholder, type .txt
v. The File Name should now look like this:
${patientId}_${message.messageId}.txt
    b. Drag the Formatted Date mapping from the Destination Mappings list to the end of the first line in the
       Template field (after “Patient Report - Created “)
    c. Change the value within the single quotes of the Formatted Date mapping that you just dragged over
       to MM/dd/yyyy (or whichever date format you choose)
       **Note:** For more information on date format patterns, see the Mirth Connect Programming Reference
    d. For each of the remaining fields in the template for the patient report, drag the corresponding
       mapping from the Destination Mappings list and drop it at the end of the line. For example, for
       “Patient ID: “, drag over the patientId mapping
    e. The Template field for the Patient Report destination should now look like this:
       Patient Report - Created ${date.get('MM/dd/yyyy')}
       -----------------------------------

```
Patient ID: ${patientId}
Last Name: ${lastName}
First Name: ${firstName}
Middle Name: ${middleName}
Date of Birth: ${dateOfBirth}
Gender: ${gender}
```
6. Save the channel
7. Deploy the channel
8. Send one or more ADT messages to the channel using HL7 Inspector (don’t forget to change the port to
    which to send to 6663, to match the port number used by the channel’s TCP Listener)


```
26 nextgen.com
```
**Results**
For each message that you send to the channel, the Received count and Sent count should each increase
by one in the Dashboard. In the “/Training/outbox” folder, you should see one new file. The name of the file
should be a combination the ID of the patient specified in the PID segment of the message sent, an
underscore, the sequential message ID, and a txt extension. For example:

```
540091_1.txt
```
**Figure 5 - 3 Example File Name**

The file should contain the patient report, displaying the patient data extracted from the message placed in
the corresponding fields. An example of this file is below in Figure 5 - 4.

```
Patient Report - Created 02 / 04 / 2019
-----------------------------------
```
```
Patient ID: 540091
Last Name: Panucci
First Name: John
Middle Name:
Date of Birth: 1949 0314
Gender: M
```
**Figure 5 - 4 Example Text Patient Report File Output**


```
27 nextgen.com
```
## Lab 6 Create XML Message Using Message Builder Transformer Steps

**Objectives**
In this lab, you will create a new channel to demonstrate the use of Message Builder transformer steps and
the outbound message to build a new outbound message from data in the inbound message. The channel
will have a TCP Listener source connector and a File Writer destination connector. In the transformer for the
File Writer, you will use an XML outbound message template and a series of Message Builder steps to
populate the new XML message. Then, you will write the newly created XML message to a file using the
File Writer.

**Figure 6 - 1 Transformers - Create XML Channel Flow**

**Estimated Time to Complete**
1 0 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Create a new channel in the Default Group named _Transformers - Create XML_
2. Configure the source connector as a TCP Listener (in MLLP transmission mode)
    a. Select TCP Listener from the Connector Type drop-down list
    b. In the Listener Settings section, change the Local Port value to 6664
3. On the Destination tab, configure the default destination as a File Writer that will generate an XML
    document file with patient data from the message
    a. Rename the destination to XML Document (optional)
    b. Change the Connector Type to File Writer
    c. In the Directory field of the File Writer Settings section, type /Training/outbox
    d. Leave the File Name field blank for now
    e. For the Template field, write the encoded data that represents the new XML document using the
       built-in “pretty printer”


```
28 nextgen.com
```
```
i. Drag-and-drop the XML Pretty Printer mapping from the Destination Mappings list into the
Template field
ii. Drag-and-drop the Encoded Data mapping from the Destination Mappings list into the
parentheses of the XML Pretty Printer mapping dragged over in the previous step
iii. The Template field for the XML Document destination should now look like this:
${XmlUtil.prettyPrint(${message.encodedData})}
```
4. Set the outbound template and create the Message Builder transformer steps for the XML Document
    destination
    a. Click Edit Transformer in the Channel Tasks menu
    b. Set the Inbound Message Template on the Message Templates tab to any HL7 ADT message
    c. Set the Outbound Message Template
       i. In the Data Type drop-down list for the outbound template, select XML
ii. Open the file “\Training\Messages\XML\Templates\Patient Template.xml”
    d. Click the Message Trees tab to view the message templates
    e. Expand the Outbound Message Template Tree by selecting the top node, XML-Message (1.0), right-
       clicking, and selecting Expand from the context menu
    f. For each node in the Outbound Message Template Tree, find the corresponding field in the Inbound
       Message Template Tree (as defined in Table 6 - 1 , below), and drag the value from the Inbound
       Message Template Tree to the node in the Outbound Message Template Tree. This will create a
       Message Builder step that maps the field in the inbound message to the corresponding field in the
       outbound message. Repeat until all fields are mapped.

```
Inbound Message Template Field Outbound Message Template Field
PID.2.1 (ID) patientId
PID.5.1 (Patient Name – Family Name) name – last
PID.5.2 (Patient Name – Given Name) name – first
PID.7.1 (Date/Time of Birth) dateOfBirth
PID.8.1 (Administrative Sex) gender
PID.11.1 (Patient Address – Street Address) address – line1
PID.11.2 (Patient Address – Other Designation) address – line2
PID.11.3 (Patient Address – City) address – city
PID.11.4 (Patient Address – State or Province) address – state
PID.11.5 (Patient Address – Zip or Postal Code) address - postalCode
Table 6 - 1 Mappings from Inbound Message Template to Outbound Message Template
```
5. Create a Mapper variable to hold the patient ID specified in PID.2.1
    a. While still on the Message Trees tab in the Transformers view, once again find PID.2.1 in the
       Inbound Message Template Tree, and drag the value to the transformers list area to create a
       Mapper step
    b. Change the name of the variable from the default value to patientId
    c. Click Back to Channel in the Mirth Connect Views menu


```
29 nextgen.com
```
6. Finish configuring the XML Document File Writer destination connector
    a. Set the File Name field to a combination of the patient ID and message ID, followed by a .xml
       extension
          iii. Drag-and-drop the patientId mapping from the Destination Mappings list to the File Name
             field
          iv. After the ${patientId} placeholder, type an underscore: _
             v. After the underscore, drag-and-drop the Message ID mapping from the Destination
                Mappings list
          vi. After the ${message.messageId} placeholder, type .xml
vii. The File Name should now look like this:
${patientId}_${message.messageId}.xml
7. Save the channel
8. Deploy the channel
9. Send one or more ADT messages to the channel using HL7 Inspector (don’t forget to change the port to
    which to send to 666 4 , to match the port number used by the channel’s TCP Listener)

**Results**
For each message that you send to the channel, the Received count and Sent should increase by one in the
Dashboard. In the “/Training/outbox” folder, you should see one new file. The name of the file should be a
combination the ID of the patient specified in the PID segment of the message sent, an underscore, the
sequential message ID, and an xml extension. For example:

```
540091_1.xml
```
**Figure 6 - 2 Example File Name**

The xml file should contain the XML document structure defined by the outbound message template, with
each element populated with data from the inbound message. An example of this file is below in Figure 6 - 3.


```
30 nextgen.com
```
```
<patient>
<patientId>540091</patientId>
<name>
<last>Panucci</last>
<first>John</first>
</name>
<dateOfBirth>19490314</dateOfBirth>
<gender>M</gender>
<address>
<line1>33 10th Ave.</line1>
<line2/>
<city>Costa Mesa</city>
<state>CA</state>
<postalCode>92330</postalCode>
</address>
</patient>
```
**Figure 6 - 3 Example XML File Output**


```
31 nextgen.com
```
## Lab 7 Modify Values in a Message Using Message Builder Transformer Steps

**Objectives**
In this lab, you will use Message Builder transformer steps to modify components of the inbound message,
before sending the modified message to the destination. The channel will have a TCP Listener source
connector and a File Writer destination connector. In the transformer for the source connector, you will
create a series of Message Builder steps using the “Map to Message” method, where each Message Builder
modifies a specific component of the message. Then, you will write the modified version of the message to
a file using the File Writer.

**Figure 7 - 1 Transformers – Modify Message Channel Flow**

**Estimated Time to Complete**
10 - 12 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Create a new channel in the Default Group named _Transformers - Modify Message_
2. Configure the source connector as a TCP Listener (in MLLP transmission mode)
    a. Select TCP Listener from the Connector Type drop-down list
    b. In the Listener Settings section, change the Local Port value to 6665
3. Create the Message Builder transformers steps to modify the message in the source connector
    a. Click Edit Transformer in the Channel Tasks menu
    b. Set the Inbound Message Template on the Message Templates tab to any HL7 ADT message
    c. Click the Message Trees tab to view the Inbound Message Template Tree
    d. Create a Message Builder step to set the value of MSH.3.1 to “Mirth Connect”
       i. In the Inbound Message Template Tree, find the node for MSH.3.1 (Sending Application –
          Namespace ID)
ii. Right click the value next to the green dot for MSH.3.1, and select “Map to Message” from
the context menu (Figure 7 - 2 )


```
32 nextgen.com
```
```
Figure 7 - 2 Inbound Message Template Tree with Map to Message for MSH.3.1
```
```
iii. In the Mapping field for the generated Message Builder step, type "Mirth Connect"
(including quotes)
iv. The Message Builder step should now look like Figure 7 - 3 , below
```
```
Figure 7 - 3 Message Builder Step to Modify MSH.3.1 with Constant Value
```
e. Create a Message Builder step to copy the value in PID.3.1 to PID.2.1
i. In the Inbound Message Template Tree, find the node for PID. 2 .1 (Patient ID – ID Number)
ii. Right click the value next to the green dot for PID.2.1, and select “Map to Message” from the
context menu
iii. In the Inbound Message Template Tree, find the node for PID.3.1 (Patient Identifier List – ID
Number)
iv. Drag from the value in the tree for PID.3.1 and drop into the Mapping field of the Message
Builder step, as shown below in Figure 7 - 4


```
33 nextgen.com
```
```
Figure 7 - 4 Dragging Value from PID.3.1 into Mapping
```
```
v. The Message Builder step should now look like Figure 7 - 5 , below
```
```
Figure 7 - 5 Message Builder Step to Copy PID.3.1 to PID.2.1
```
f. Create Message Builder steps to convert PID.5.1 (Family Name) and PID.5.2 (Given Name) to
uppercase
i. In the Inbound Message Template Tree, find the node for PID. 5 .1 (Patient Name – Family
Name)
ii. Right click the value next to the green dot for PID. 5 .1, and select “Map to Message” from the
context menu
iii. Drag from the value in the tree for PID.5.1 (the same component) and drop into the Mapping
field of the Message Builder step
iv. Edit the code in the Mapping field so that it looks like the following (the bolded part is the
code to add):
msg['PID']['PID. 5 ']['PID. 5 .1'].toString() **.toUpperCase()
Note:** You must type the code _exactly_ as indicated, including case
v. The Message Builder step should now look like Figure 7 - 6 , below


```
34 nextgen.com
```
```
Figure 7 - 6 Message Builder Step to Convert Value of PID.5.1 to Uppercase
```
```
vi. Repeat steps i-iv, above, for PID.5.2 (Patient Name – Given Name)
g. Create a Message Builder step to remove dashes from PID.19.1 (Social Security Number)
i. In the Inbound Message Template Tree, find the node for PID. 19 .1 (SSN Number - Patient –
Value)
ii. Right click the value next to the green dot for PID. 19 .1, and select “Map to Message” from
the context menu
iii. Drag from the value in the tree for PID. 19 .1 (the same component) and drop into the
Mapping field of the Message Builder step
iv. Edit the code in the Mapping field so that it looks like the following (the bolded part is the
code to add):
msg['PID']['PID. 19 ']['PID. 19 .1'].toString() .replace(/-/g, "" )
Note: You must type the code exactly as indicated, including case
v. The Message Builder step should now look like Figure 7 - 7 , below
```
```
Figure 7 - 7 Message Builder step to Remove Dashes from SSN in PID.19.1
```
```
h. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel view
```
4. On the Destination tab, configure the default destination as a File Writer that will write the modified
    message to a file
    a. Rename the destination to Write Modified HL7 to File
    b. Change the Connector Type to File Writer
    c. In the Directory field of the File Writer Settings section, type /Training/outbox
    d. For the File Name field, define the name as message unique ID followed by a .hl7 extension
       i. Drag-and-drop the Unique ID mapping from the Destination Mappings list
ii. Type .hl7 after the ${UUID} placeholder


```
35 nextgen.com
```
```
e. For the Template field, drag-and-drop the Encoded Data mapping from the Destination Mappings list
```
5. Save the channel
6. Deploy the channel
7. Send one or more ADT messages to the channel using HL7 Inspector (don’t forget to change the port to
    which to send to 6665, to match the port number used by the channel’s TCP Listener)

**Results**
For each message that you send to the channel, the Received count and Sent should increase by one in the
Dashboard. In the “/Training/outbox” folder, you should see one new file for each message sent. Each file
should contain the modified version of the message.

You can compare the original version of the message to the modified version one of two ways:

- Compare the message in the output file to the original message file that you sent from HL7 Inspector
- In the Administrator, go to the Channel Messages View (select View Messages from the Dashboard
    Tasks menu), select the Source connector message for one of the messages processed, and on the
    Messages tab, click between the Raw and Encoded radio buttons

Figure 7 - 8 and Figure 7 - 9 , below, show an example of how the ADT message for Hermes Conrad was
modified, with Figure 7 - 8 showing the original message and Figure 7 - 9 showing the modified message.
Bold text highlights the values in each message that were modified.

```
MSH|^~\&| ADTSENDER |Hospital A|||20150601132323||ADT^A03|HCONRAD-0040|T|2.2|8092
EVN|A03|20150601132323|||mr.cfar
PID|| 880040 |741012606|| Conrad ^ Hermes ^^||19640202|M||2054-5|...||ENG|P|OTH|0040| 741 - 01 - 2606 ||
```
**Figure 7 - 8 Original (Raw) Message**

```
MSH|^~\&| Mirth Connect |Hospital A|||20150601132323||ADT^A03|HCONRAD-0040|T|2.2|8092
EVN|A03|20150601132323|||mr.cfar
PID|| 741012606 |741012606|| CONRAD ^ HERMES ^^||19640202|M||2054-5|...||ENG|P|OTH|0040| 741012606 ||
```
**Figure 7 - 9 Modified (Encoded) Message**


```
36 nextgen.com
```
## Lab 8 Create and Populate a Channel Group

**Objectives**
In this lab, you will create a channel group and then move three of your existing channels into that group.
The new channel group will contain the channels created in the three previous labs (Lab 5, Lab 6, and Lab
7 ), which are all related to transformers. Finally, you will export the channel group, showing that a single
action can be applied to the entire group without having to directly apply the action to each individual
channel within the group.

**Estimated Time to Complete**
5 minutes

**Tools Used**

- Mirth Connect Administrator
- Notepad++

**Step-By-Step**

1. Navigate to Channels view by clicking Channels in the Mirth Connect menu
2. Create a new channel group
    a. In the Group Tasks menu, click New Group
    b. In the Name field of the Channel Group Details dialog, type Transformer Channels (Figure 8 - 1 )

```
Figure 8 - 1 Channel Group Details
```
```
c. Click OK to create the group
```

```
37 nextgen.com
```
```
d. You should now see the empty channel group in the Channels list (Figure 8 - 2 )
```
```
Figure 8 - 2 Empty Channel Group in Channels List
```
3. Add the channels from the three previous labs to the new group
    a. While pressing the Ctrl (control) key, click each of the following channels:
       - _Transformers - Create Text Report_ (created in Lab 5)
       - _Transformers - Create XML_ (created in Lab 6)
       - _Transformers - Modify Message_ (created in Lab 7)
       **Note:** The above channel names are the names of the channels as specified in each lab. If you
       named your channels differently, use those names.
    b. In the Group Tasks menu, click Assign To Group
    c. In the Channel Group Assignment dialog that appears, select the channel group created in Step 2
       (Figure 1 - 1 Figure 8 - 3 )

```
Figure 8 - 3 Channel Group Assignment
```
```
d. In the Group Tasks menu, click Save Group Changes
e. In the Channels list, you should now see the three selected channels as part of the Transformer
Channels group (Figure 8 - 4 )
```
```
Figure 8 - 4 Channel Group Containing Transformer Channels
```

```
38 nextgen.com
```
4. Export the channel group to a file
    a. In the Channels list, select the Transformer Channels group (Figure 8 - 5 )

```
Figure 8 - 5 Channel Group Selected in Channels List
```
```
b. In the Group Tasks menu, click Export Group
c. In the File Save dialog, navigate to “C:\Training”
d. Click Save
e. In the confirmation dialog that appears (Figure 8 - 6 ), click OK to dismiss
```
```
Figure 8 - 6 Channel Group Export Confirmation
```
**Results**
In addition to seeing the channel group in both the Channels and Dashboard views, you should now also
see the export file for the channel group, named “Transformer Channels.xml” in the “/Training” folder. If you
view the file contents using Notepad++ (or another text editor), you can see the XML that defines both the
channel group as well as the channels within the group (Figure 8 - 7 , on page 39 ).


```
39 nextgen.com
```
<channelGroup version="3.11.0">
<id>5d2e91be- 2600 - 4 cf3-b71a-61707c2abc6b</id>
<name>Transformer Channels</name>
<revision>1</revision>
<lastModified>
<time>1632496492270</time>
<timezone>America/Los_Angeles</timezone>
</lastModified>
<description></description>
<channels>
<channel version="3.11.0">
<id>a39f6c71-03d1- 4698 - bf0e-4579c4bbb74f</id>
<nextMetaDataId>3</nextMetaDataId>
<name> **Transformers - Create Text Report** </name>
...
</channel>
<channel version="3.11.0">
<id>33c9ef7a-4eda- 4314 - 9db8-16c26689721c</id>
<nextMetaDataId>2</nextMetaDataId>
<name> **Transformers - Create XML** </name>
...
</channel>
<channel version="3.11.0">
<id>980d7c09- 6925 - 4ea1-a4a7-42a7e5d5b226</id>
<nextMetaDataId>2</nextMetaDataId>
<name> **Transformers - Modify Message** </name>
...
</channel>
</channels>
</channelGroup>

**Figure 8 - 7 Example Channel Group Export Contents**


```
40 nextgen.com
```
## Lab 9 Receive, Send Messages Using TCP Connectors in MLLP Transmission Mode

**Objectives**
In this lab, you will create a channel that listens for messages using a TCP Listener in MLLP transmission
mode and sends the message to an MLLP server on a given destination system using the TCP Sender (also
in MLLP transmission mode). You will also use a Message Builder transformer step to change the Sending
Application field (MSH.3.1) to your student number. Additionally, you will change the response that is sent
back from the channel to use the response received by the destination connector, instead of the auto-
generated ACK.

To send to the channel’s TCP Listener, you will once again use the HL7 Inspector.

**Figure 9 - 1 TCP Lab Processing Flow**

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector

**Step-By-Step**

1. Create a new channel in the Default Group named _MLLP to MLLP_
2. Configure the source connector as a TCP Listener (in MLLP transmission mode)
    a. Select TCP Listener from the Connector Type drop-down list
    b. In the Listener Settings section, change the Local Port value to 6666
3. Add a transformer step on source connector to change the Sending Application field to your student
    number
    a. Click Edit Transformer in the Channel Tasks menu
    b. Set the Inbound Message Template to any HL7 ADT message
    c. Click the Message Trees tab to view the Inbound Message Template Tree
    d. Expand the Inbound Message Tree so that the green-dotted value under MSH.3.1 is visible, by
       successively clicking the “+” next to the MSH segment, then the MSH.3 field, then the MSH.3.1
       component
    e. Right-click on the value under MSH.3.1, indicated by the green dot (Figure 9 - 2 )


```
41 nextgen.com
```
```
Figure 9 - 2 Right-Clicking on MSH.3.1 and Selecting Map to Message
```
```
f. From the pop-up context menu, select Map to Message
g. In the Mapping field for the generated Message Builder step, type "sX" (including quotes), where X
is your given student number. For example, if your student number is 13, type "s13"
h. Click Back to Channel in the Mirth Connect Views menu
```
4. Configure the TCP Listener to respond from the destination’s response
    a. In the Source Settings section of the source connector, select “Destination 1” from the Response
       drop-down list
5. Configure the destination connector as a TCP Sender (in MLLP transmission mode) that will send to the
    destination system
    a. On the Destinations tab, rename the default connector to Send to MLLP Server
       **Note:** In Step 4 , you configured the source connector to respond from “Destination 1”. Renaming
       the destination from “Destination 1” to “Send to MLLP Server”, will not affect that setting. If you were
       to go back to the Source tab, you would see that the Response drop-down list now has “Send to
       MLLP Server” selected.
    b. Select TCP Sender in the Connector Type drop-down list
    c. In the Remote Address field of the TCP Sender Settings section, type the address for the destination
       system. s 1 a.mirthcorp.com or mirth.enterprisepreview.nextgen.com
    d. In the Remote Port field, type 9100
6. Save the channel
7. Deploy the channel
8. Configure HL7 Inspector to send to the channel on port 666 6
9. Send any HL7 message to the channel using HL7 Inspector


```
42 nextgen.com
```
**Results**
The Dashboard statistics for the channel should show 1 message received and 1 message sent. Switch to
Channel Messages view to see the message details. Select the Source row for the message you just sent.
On the Messages tab, click the Encoded radio button to view the encoded message data. You should see
your student number in place of the original Sending Application value in MSH.3.1.

For example, if the MSH segment of the message that you sent to the channel (in other words, the raw
message) looks like this:

```
MSH|^~\&| EPIC |Hospital B|KEANE|KEANE|20090601093321|I000007|ADT^A08|...
```
**Figure 9 - 3 Example MSH segment in the Raw Message with MSH.3.1 highlighted**

The resulting MSH segment in the Encoded Message might look like this (where X is your student number):

```
MSH|^~\&| sX |Hospital B|KEANE|KEANE|20090601093321|I000007|ADT^A08|...
```
**Figure 9 - 4 Example MSH segment in the Encoded Message with the value of MSH.3.1 changed**

In the HL7 Inspector, you should see the ACK message sent back from your channel. In the MSA segment,
you should see an acknowledgement code of AA in MSA.1.1 and the following message in MSA.3.1:

“Successfully received message for Student X.”

Where X is your student number.

If you did not correctly replace the sending application in MSA.3.1 with your student number, you would
instead see the following message in MSA.3.1:

“Expected student number not found in MSH.3.1. Check Step 3 of the lab.”

If you received this message instead, please review step 2 and make any necessary changes to your
channel.


```
43 nextgen.com
```
## Lab 10 Create a Channel that Reads a File from a Local Folder and Writes to an SFTP Server

**Objectives**
In this lab, you will create a channel with a File Reader source connector and a File Writer destination
connector. In previous labs, you’ve used the File Writer to write a file to the local file system. This channel
will demonstrate one of the other file connector capabilities—to connect to an SFTP server. You will also
use a File Reader source connector for the first time to poll for new files from your local file system.

**Figure 10 - 1 Local Folder to FTP Flow**

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer
- FileZilla FTP Client (optional)

**Step-By-Step**

1. Create a new channel in the Default Group named _Local Folder to FTP_
2. Configure the source connector as a File Reader that reads from a local folder
    a. On the Source tab, select File Reader in the Connector Type drop-down list
    b. In the Directory field of the File Reader Settings section, type /Training/inbox
    c. In the Filename Filter Pattern field, type *.hl7
    d. In the After Processing Action drop-down list, select Move


```
44 nextgen.com
```
e.
Define the Move-to Directory as /Training/processed/${channelName}
i.
In the Move-to Directory field, type /Training/processed/
ii.
From the variable box to the right of the Move-to-
Directory field, select channelName and
drag-and-drop it after the end of the path in the Move-to Directory field
f.
Define the Move-to File Name as the name of the file read by the File Reader, prefixed with the
current count of files processed: ${COUNT}_${originalFileName}
i.
From the variable box to the right of the Move-to File Name field, select COUNT and drag-
and-drop it into the Move-to File Name field to insert the ${COUNT} placeholder
ii.
After the ${COUNT} placeholder, type an underscore character (_)
iii.
Drag originalFilename from the variables box
and drop it into the Move-to File Name field
after the underscore. The Move-to File
Name field should now contain:
${COUNT}_${
originalFilename}
3.
Configure the destination connector as a File Writer that writes to an SFTP
server
a.
On the Destinations tab, rename the default File Writer destination to SFTP Server
b.
Change the Connector Type to File Writer
c.
In the Method drop-down list
in the File Writer Settings section, select sftp
d.
In the sftp:// field, type
Host Address: localhost

e.^ In the second sftp:// field^ (after the /), type^ the path provided on your _Student Information_^ handout^
f.^ For the File Name field, drag-and-drop Original File Name from the Destination Mappings list to
insert the ${originalFilename} placeholder^
g.^ In the Username field, replace the default contents with^ the username from your _Student Information_^
handout^
h.^ In the Password field, replace the default contents the password from your _Student Information_^
handout^
i.^ Click the Test Write button (to the right of the Method drop-down list). After a few seconds, a pop-up
should appear indicating that you have^ successfully connected.^
j.^ For the Template field, drag-and-drop Encoded Data from the Destination Mappings list^
4.^ Save the channel^
5.^ Deploy the channel^
6.^ View the current contents of your student folder on the FTP server (optional)^ a.
Start^ the FileZilla FTP Client applicationinstalled^ on your student computer^

```
Figure 10 - 2 FileZilla FTP Client in Windows Taskbar
```
```
b. In the FileZilla application, beneath the menu bar and tool bar you should see fields in which to enter
values for Host, Username, Password and Port (Figure 10 - 3 ). Enter the corresponding values from
your Student Information handout
```
```
Username: preview
Password: Pr#view 1
Port: 22
Folder Path: /users/preview/files/outbox
```

```
45 nextgen.com
```
```
Figure 10 - 3 FileZilla Connection Settings
```
```
c. Click the Quickconnect button to the right of the Port field to connect
d. In the Remote Site pane on the right-hand side, you should see a single folder called outbox. If you
click into this folder, it should currently be empty.
```
7. Copy one or more sample HL7 message files from the “/Training/Messages/HL7” folder on your local
    computer to the “/Training/inbox” folder, also on your local computer (not the inbox on the FTP server)

**Results**
Within a few seconds of copying the HL7 messages files to the inbox folder, the channel will process them.
The Dashboard statistics for the channel in the Administrator should show Received and Sent counts equal
to the number of HL7 message files copied to the inbox.

Using Windows File Explorer to view your local “/Training/inbox” folder, you should see that the folder is now
empty, and the local “/Training/processed” folder now contains a new subfolder that matches the name of
your channel. Within this folder, you should see the files that were processed (that is, read from the inbox
by your channel’s File Reader), each prefixed with a sequential number (generated by the COUNT variable).

Next, using the FileZilla FTP Client to view the outbox folder, you should see the same HL7 files read by the
channel, each written using the original file name. Note that if you have already viewed the contents of the
outbox folder on the FTP server, you will need to refresh the contents of that folder by clicking the Refresh
button in FileZilla. This is the button on the toolbar with blue and green arrows pointing in opposite
directions (see Figure 10 - 4 , below).

**Figure 10 - 4 FileZilla Refresh Button**


```
46 nextgen.com
```
## Lab 11 Generate HL7 Messages from Rows in a Database Table

**Objectives**
In this lab, you will create a channel that uses a Database Reader to read from a table of new patients, and
uses Message Builder transformer steps to create an outbound ADT message from that data and writes it to
a file. For each row read from the database table, a new file containing a single HL7 message should be
created.

To prevent the same rows from being processed over and over, you will use the Database Reader’s Post-
Process SQL script to update each row after it has been processed to indicate such.

If you wish to attempt this lab in your own local environment, the script to create the database table required
by this lab is contained in the file “New Patients Table.sql”, located in the SQL subfolder of your Training
folder.

**Figure 11 - 1 Database Reader Lab Processing Flow**

**Estimated Time to Complete**
15 - 20 minutes

**Tools Used**

- Mirth Connect Administrator
- SQuirreL SQL Client (optional)
- Windows File Explorer

**Step-By-Step**

1. Create a new channel in the Default Group named _Database Reader_


```
47 nextgen.com
```
2. Configure the basic Database Reader source connector settings
    a. On the Source tab, select Database Reader in the Connector Type drop-down list
    b. In the Driver drop-down list in the Database Reader Settings section, select PostgreSQL
    c. Click the Insert URL Template button
    d. In the URL field, edit the URL template so that it matches the following:
       jdbc:postgresql://localhost:5432/mirthtraining
    e. In the Username field, type mirthtraining
    f. In the Password field, type mirthtraining
    g. Your configuration settings should now look like Figure 11 - 2 , below

```
Figure 11 - 2 Database Reader Settings
```
3. Generate the SQL query to select unprocessed rows from the NewPatients table
    a. Click the Select button above the SQL editor on the right-hand side. This opens the SQL Creation
       dialog (Figure 11 - 3 )
    b. In the “Filter by” field of the SQL Creation dialog, type newpatients (optional)
    c. Click the Get Tables button to get the table metadata

```
Figure 11 - 3 The SQL Creation Dialog (NewPatients Table)
```

```
48 nextgen.com
```
```
d. Select all of the columns in the NewPatients table, except “processed”, by checking the box to the
left of each column name. Alternatively, you could check the box to the left of “newpatients” (the
table name) and uncheck the “processed” column.
e. Click the Generate button
f. Edit the inserted SELECT statement to select on rows marked as unprocessed by adding the
following line:
WHERE processed = false
Note: SQL is case-insensitive. Therefore, the case used for adding the above code is unimportant.
The SELECT statement should now look like the following:
```
```
SELECT newpatients.newpatientid AS newpatients_newpatientid,
newpatients.lastname AS newpatients_lastname, newpatients.firstname AS
newpatients_firstname, newpatients.middlename AS newpatients_middlename,
newpatients.gender AS newpatients_gender, newpatients.dateofbirth AS
newpatients_dateofbirth, newpatients.ssn AS newpatients_ssn
FROM newpatients
WHERE processed = false
```
```
Figure 11 - 4 Final SELECT Statement
```
4. Generate the SQL statement to update selected rows to mark them as processed
    a. Change the Run Post-Process SQL setting to After Each Message
    b. Click the Update button above and to the right of the Run Post-Process SQL editor
    c. In the SQL Creation dialog, click the Get Tables button
    d. Check the box next to the “processed” column in the NewPatients table
    e. Click the Generate button
    f. Edit the inserted UPDATE statement so that it looks like the following:
       UPDATE newpatients
       SET processed = true
       WHERE newpatientid =
    g. Insert the variable placeholder for the patient ID from the message by selecting
       newpatients_newpatientid in the box to the right of the Run Post-Process SQL editor and dragging
       and dropping it into the WHERE clause after the equals sign. The UPDATE statement should now
       look like the following:

```
UPDATE newpatients
SET processed = true
WHERE newpatientid = ${newpatients_newpatientid}
```
```
Figure 11 - 5 Final UPDATE Statement
```
5. Generate the outbound ADT message using Message Builder transformer steps
    a. While still in the source connector, click Edit Transformer in the Channel Tasks menu
    b. On the Message Templates tab, verify that the Data Type for the Outbound Message Template is
       set to HL7 v2.x (this is the default)
    c. Set the outbound template to the message in the file “/Training/Messages/HL7/Templates/ADT
       Template.hl7”


```
49 nextgen.com
```
```
d. On the Message Trees tab, create Message Builder steps by selecting a node from the Inbound
Message Template Tree and dragging and dropping it onto the corresponding node in the Outbound
Message Template Tree, as indicated in Table 11 - 1 , below:
```
```
Inbound Message Template Element Outbound Message Template Component
```
```
newpatients_newpatientid PID.2.1 (ID)
newpatients_lastname PID.5.1 (Patient Name – Family Name)
newpatients_firstname PID.5.2 (Patient Name – Given Name)
```
```
newpatients_middlename PID.5.3 (Patient Name Given Names or Initials Thereof)–^ Second and Further
```
```
newpatients_gender PID.8.1 (Administrative Sex)
newpatients_dateofbirth PID.7.1 (Date/Time of Birth)
newpatients_ssn PID.19.1 (SSN Number – Patient)
Table 11 - 1 Mappings from Inbound Message Template to Outbound Message Template
```
```
e. Click Back to Channel in the Mirth Connect Views menu
```
6. Configure the destination connector as a File Writer to write the generated ADT message
    a. On the Destinations tab, rename the default File Writer destination to Write HL7 File
    b. Change the Connector Type to File Writer
    c. In the Directory field, type /Training/outbox
    d. For the File Name field, define the name as message unique ID followed by a .hl7 extension
       iv. Drag-and-drop the Unique ID mapping from the Destination Mappings list
          v. Type .hl7 after the ${UUID} placeholder
    e. For the Template field, drag-and-drop the Encoded Data mapping from the Destination Mappings list
7. Save the channel (but do not deploy the channel yet)
8. View the current state of the data in the NewPatients table (optional)
    a. Open the SQuirreL SQL Client application by clicking the icon indicated in Figure 11 - 6 in the
       Windows Taskbar. Alternatively, you could also open SQuirreL by selecting it from the Windows
       Start menu, or by double-clicking the SQuirreL shortcut on your desktop.

```
Figure 11 - 6 SQuirreL SQL Client in Windows Taskbar
```
```
b. In the Alias pane, select Mirth Training Database (Figure 11 - 7 ).
Note: If the Aliases pane is not visible, click the Aliases tab along the left-hand side of the window to
open it.
```

```
50 nextgen.com
```
```
Figure 11 - 7 Mirth Training Database Selected in SQuirreL SQL Client
```
c. Right-click the Mirth Training Database alias and select Connect from the context menu.

Alternatively, you can click the button from the Aliases toolbar.
d. In the “Connect to” dialog that appears (Figure 11 - 8 ), click the Connect button to connect to the
database and open the session window

```
Figure 11 - 8 Connect to Database Dialog
```
e. Once the connection is established, and the connection window opens, click the SQL tab to display
the SQL query editor (if it is not already open).
f. In the text area of the SQL editor, type the following SQL query:

```
SELECT * FROM NewPatients
```
g. With the cursor still on the line that you just typed, press Ctrl-Enter to execute the query (or press the
button on the toolbar that looks like a person running)


```
51 nextgen.com
```
```
h. In the results pane of the window, you should see four rows of patient data (Figure 11 - 9 on page 51 ).
Note that the last column, Processed, shows a value of false for each row.
```
```
Figure 11 - 9 NewPatients Query with Results
```
9. Deploy the channel

**Results**
Within a few seconds of deployment, the channel will read the four rows in the database table, generate the
outbound ADT messages from the data and write the messages out to files. The Dashboard statistics for
the channel in the Administrator should show 4 messages received and 4 messages sent. In the Channel
Messages view, you can view the data read from the database for each row in XML format, as well as the
HL7 messages created from the data.

If you execute the query of the NewPatients table in SQuirreL SQL Client once again, you should now see
that the Processed column for each row is now set to true.

Finally, you should see four new files in the “/Training/outbox” folder. Each of these files should contain an
HL7 ADT message with the appropriate fields set to the corresponding values read from the database. The
remaining fields (that is, the fields that weren’t specifically set with a Message Builder step) should remain
as they were in the ADT outbound message template. See Figure 11 - 10 on page 52 for an example of one
of the messages.


```
52 nextgen.com
```
```
MSH|^~\&|Mirth Connect||||||ADT^A01||P|2.5|||
PID|1|12345|||Fry^Philip^J^^^||1971- 10 - 15|M|||^^^^^||||||||123- 45 - 6789||
PV1|1||||||^^^||||||||||||||||||||||||||||||||||||||
```
**Figure 11 - 10 Example HL7 Message Generated from Database Row for Patient Philip Fry**


```
53 nextgen.com
```
## Lab 12 Extract Data from Inbound HL7 Messages, Write Data to Database

**Objectives**
In this lab, you will create a channel that receives HL7 messages over MLLP, and extracts patient data from
the messages and stores that data into Mapper variables. The data in those variables are then written to a
database, using the Database Writer. For each HL7 message received, one new row should be inserted
into the database table.

If you wish to attempt this lab in your own local environment, the script to create the database table required
by this lab is contained in the file “Patients Table.sql”, located in the SQL subfolder of your Training folder.

**Figure 12 - 1 Database Writer Lab Processing Flow**

**Estimated Time to Complete**
10 - 12 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- SQuirreL SQL Client

**Step-By-Step**

1. Create a new channel in the Default Group named Database Writer
    a. Configure the source connector as a TCP Listener in MLLP transmission mode
    b. On the Source tab, change the Connector Type to TCP Listener
    c. Update the Local Port value to 6667
2. Create the Mapper variables that will hold the data from the inbound message to write into the database
    a. While still on the Source tab, click Edit Transformer in the Channel Tasks menu
    b. Set the Inbound Message Template to any HL7 ADT message
    c. Click the Message Trees tab to view the Inbound Message Template Tree


```
54 nextgen.com
```
```
d. For each of the entries in the following table, create a Mapper variable by finding the listed HL7
component in the tree, then dragging and dropping into the transformers list area. Then rename the
created variable as indicated
HL7 Component Rename Variable To
PID.2.1 patientId
PID.5.1 lastName
PID.5.2 firstName
PID.5.3 middleName
PID.7.1 dateOfBirth
PID.8.1 gender
PID.11.1 address1
PID.11.2 address2
PID.11.3 city
PID.11.4 state
PID.11.5 postalCode
Table 12 - 1 Mappings from HL7 Message to Mapper Variables
```
```
e. Once you have created each of the Mapper variables in the table above, click Back to Channel in the
Mirth Connect Views menu
```
3. Configure the destination connector as a Database Writer
    a. On the Destinations tab, rename the destination to Write Patient Data to Database
       (optional)
    b. Change the Connector Type to Database Writer
    c. In the Driver drop-down list of the Database Writer Settings section, select PostgreSQL
    d. Click the Insert URL Template button
    e. In the URL field, edit the URL template so that it matches the following:
       jdbc:postgresql://localhost:5432/mirthtraining
    f. In the Username field, type mirthtraining
    g. In the Password field, type mirthtraining
4. Generate the SQL statement to insert the patient data into the database table
    a. Click the Insert button above the SQL editor on the right-hand side. This opens the SQL Creation
       dialog (Figure 12 - 2 )
    b. In the “Filter by” field of the SQL Creation dialog, type patients (optional)
    c. Click the Get Tables button to get the table metadata


```
55 nextgen.com
```
```
Figure 12 - 2 The SQL Creation Dialog (Patients Table)
```
d. Select all of the columns in the Patients table, _except_ “seqid”, “dateadded”, and “datemodified”, by
checking the box to the left of each column name. Alternatively, you could check the box to the left
of “patients” (the table name), and then uncheck the “seqid”, “dateadded”, and “datemodified”
columns.
e. Click the Generate button. In the SQL editor, you should now see the following incomplete SQL
code ( **Note:** The code here may look slightly different due to text wrapping):

```
INSERT INTO patients (patientid, lastname, firstname, middlename,
dateofbirth, gender, address1, address2, city, state, postalcode)
VALUES (, , , , , , , , , , )
```
```
Figure 12 - 3 Incomplete SQL Code
```
f. Drag each Mapper variable from the Destination Mappings list into the generated INSERT
statement, in the correct position in the statement’s empty comma-separated VALUES list. This
should be done in the same order as the corresponding columns in the statement’s columns list. For
example, patientid is the first column listed in the INSERT statement, so drag the patientId Mapper
variable over into the first position in the VALUES list.
The resulting statement should look like the following, with the added variable placeholders shown in
bold font ( **Note:** The code here may look slightly different due to text wrapping):


```
56 nextgen.com
```
```
INSERT INTO patients (patientid, lastname, firstname, middlename,
dateofbirth, gender, address1, address2, city, state, postalcode)
VALUES ( ${patientId} , ${lastName} , ${firstName} , ${middleName} ,
${dateOfBirth} , ${gender} , ${address1} , ${address2} , ${city} , ${state} ,
${postalCode} )
```
```
Figure 12 - 4 Final INSERT Statement
```
5. Save the channel
6. Deploy the channel
7. Configure HL7 Inspector to send to the channel on port 666 7
8. Send any HL7 message to the channel using HL7 Inspector

**Results**
You can view the output of the channel using SQuirreL SQL Client. If you do not still have a connection to
the mirthtraining database in SQuirreL, see step 8 of Lab 11 (on page 49 ) to create the connection.

In SQuirreL, go to the SQL tab and execute the following query:

SELECT * FROM Patients

For each message that you sent to the channel, you should see a new row inserted into the Patients table
containing the data extracted from the message.

Additionally, in the Administrator, the Sent and Received statistics for the channel should increment by one
for each message that you send to the channel.

**Note:** Because the Database Writer is performing an insert without checking to see if the patient data
already exists in the table, processing the same message twice, or different messages for the same user,
will result in multiple rows for that user. Only the SeqID, DateAdded, and DateModified columns will be
different.


```
57 nextgen.com
```
## Lab 13 Generate a Patient Report PDF Document Using the Document Writer

**Objectives**
In this lab, you will create a channel that uses the Document Writer destination connector to create a patient
report PDF document from patient data in the inbound message. You will create the PDF document as both
a file and an attachment. The PDF attachment that you create in this lab will also be used in a supplemental
lab, Lab 25, on page 104. As in previous labs, you will use Mapper transformer steps to extract the required
patient data from the message.

**Figure 13 - 1 Document Writer Lab Processing Flow**

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer
- Any text editor, such as Notepad++
- Adobe Acrobat Reader

**Step-By-Step**

1. Create a new channel in the Default Group named _PDF Writer_
2. Leave the source connector configured as a Channel Reader
3. Configure the destination connector as a PDF document writer
    a. Rename the destination to Generate PDF (optional)
    b. Change the Connector Type to Document Writer
    c. In the Document Writer Settings section, change the Output setting to “Both”
    d. In the Directory field, type /Training/outbox
    e. For now, leave the File Name setting blank. This will be set in Step 5
    f. Open the file “PDF Patient Report Template.html” from the “/Training/Miscellaneous” folder in a text
       editor, and copy and paste it into the HTML Template field


```
58 nextgen.com
```
```
Note: To open the file in a text editor such as Notepad++, find the file in Windows Explorer, right-
click with your mouse, and select Edit with Notepad++ from the context menu
```
4. Extract the patient data required for the report from the inbound message using Mapper transformer
    steps
    a. On the Destination tab, click Edit Transformer in the Channel Tasks menu
    b. Set the inbound message template to any ADT message in the “/Training/Messages/HL7” folder
    c. For each of the PID components in Table 13 - 1 on page 58 , create a Mapper variable, renaming it to
       the value in the “Rename Variable To” column
          **HL7 Component Rename Variable To**
          PID.2.1 patientId
          PID.5.1 lastName
          PID.5.2 firstName
          PID.5.3 middleName
          PID.7.1 dateOfBirth
          PID.8.1 gender
          PID.13.1 phoneNumber
       **Table 13 - 1 Mappings from HL7 Message to Mapper Variables**

```
d. Click Back to Channel in the Mirth Connect Views menu to return to the Destinations tab
```
5. Finish configuring the PDF Writer destination as follows:
    a. Set the File Name to the patient ID (stored in the patientId Mapper variable created in Step 4.c),
       followed by an underscore, followed by the Message ID destination mapping, followed by a .pdf
       extension:
       ${patientId}_${message.messageId}.pdf
          i. Drag the patientId Mapper variable from Destination Mappings into the File Name field
ii. After the patientId variable, type an underscore character
iii. Drag the Message ID variable from Destination Mappings and drop it after the underscore
character
iv. After the Message ID variable, type the correct PDF extension: .pdf
    b. For each of the fields in the template, drag the corresponding destination mapping and drop it into
       the body of the empty <td></td> tag
    c. After populating the HTML template as defined in Step 5.b, the HTML Template of the Document
       Writer should now look like Figure 13 - 2 on page 59
       **Note:** Variable placeholders dragged from the Destination Mappings list are shown in bold font


```
59 nextgen.com
```
```
<table style="margin: 0; border: 1px solid #000000; padding: 0;">
<tr style="background: #e6e6e6;">
<td colspan="2" style="margin: 0; padding: 5px 5px 1px 5px;
border-bottom: 1px solid #b5b5b5; text-align: center">
<b>Patient Report</b></td>
</tr>
<tr style="background: #b8d1f3;">
<td>Patient ID:</td>
<td> ${patientId} </td>
</tr>
<tr style="background: #dae5f4;">
<td>First Name:</td>
<td> ${firstName} </td>
</tr>
<tr style="background: #b8d1f3;">
<td>Last Name:</td>
<td> ${lastName} </td>
</tr>
<tr style="background: #dae5f4;">
<td>Middle Name:</td>
<td> ${middleName} </td>
</tr>
<tr style="background: #b8d1f3;">
<td>Date of Birth:</td>
<td> ${dateOfBirth} </td>
</tr>
<tr style="background: #dae5f4;">
<td>Gender:</td>
<td> ${gender} </td>
</tr>
<tr style="background: #b8d1f3;">
<td>Home Phone:</td>
<td> ${phoneNumber} </td>
</tr>
</table>
```
```
Figure 13 - 2 Final Document Writer HTML Template
```
6. Save the channel
7. Deploy the channel
8. Use the Dashboard’s Send Message tool to send one or more ADT, ORU or OUL messages (or any
    other message with a PID segment) to the channel
    a. In the Administrator’s Dashboard view, select the _PDF Writer_ channel
    b. In the Dashboard Tasks menu, click Send Message. This opens the Message dialog (Figure 13 - 3 )


```
60 nextgen.com
```
```
Figure 13 - 3 Send Message
```
```
c. In the dialog, click the Open Text File... button, and browse to and open any of the sample HL7
messages in “C:\Training\Messages\HL7”
d. Click the Process Message button to send the message to the channel
```
**Results**
For each message sent to the channel, you should see the received and sent counts for the channel
increased by one in the Dashboard. In the /Training/outbox folder, you should see a new PDF file for each
message sent, with the name of each file being the patient ID value from PID.2.1, followed by an
underscore, followed by the message ID. For example, 111987_1.pdf.

In each file, you should see a formatted table containing the patient data. Figure 13 - 7 (on page 61 ) shows
an example of what the contents of your PDF file should look like.

Next, go into the Channel Messages view for this channel by selecting the channel in the Dashboard and
clicking View Messages in the Dashboard Tasks menu. Select the row for the “Generate PDF” connector
(assuming that is what you named your Document Writer destination connector). On the Messages tab,
select the Response radio button to view the destination’s response data.

For the response status, you should see a message similar to the following:

```
SENT: Document successfully written to attachment and file: /Training/outbox/111987_1.pdf
```
**Figure 13 - 4 Example Response Status for Document Writer Destination**

For the Response, you should see the ID of the attachment that was generated for the PDF, similar to the
following:


```
61 nextgen.com
```
```
${ATTACH:25491429-b368-412a-b4be-c41ec6a01841}
```
**Figure 13 - 5 Example Response Message for Document Writer Destination**

Finally, you should also be able to view the PDF itself within the Channel Messages view. With the row for
the “Generate PDF” connector still selected, click the Attachments tab. There, you should see a single
attachment listed, with the same ID as what is in the destination’s response message. Select the row for the
attachment and click View Attachment in the Message Tasks menu. This displays the Select Attachment
Viewer dialog, as shown below in Figure 13 - 6. Leave the selection as “PDF Viewer” and click OK. This
should open a viewer that displays the same PDF document as the file that was generated, as shown below
in Figure 13 - 7.

**Figure 13 - 6 Select Attachment Viewer Dialog**

**Figure 13 - 7 Example Output from PDF Writer Channel**


```
62 nextgen.com
```
## Lab 14 Create and Use Configuration Map Variables

**Objectives**
In this lab, you will create a handful of Configuration Map variables to use for connector properties. Once
created and saved, you will then use them in place of hard-coded values in the channel that you created in
Lab 3 (page 11 ). Finally, you will test the channel by sending a message to it, and verify that it still works
exactly the same using the variables in place of the hard-coded values.

**Estimated Time to Complete**
7 - 8 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Create Configuration Map variables in the Settings view
    a. In the Administrator, click Settings in the Mirth Connect menu to switch to the Settings view
    b. Click the Configuration Map tab
    c. For each of the key/value pairs in Table 14 - 1 (below), perform the following steps:
       i. Click the Add button to the right of the Configuration Map table to add a new row (i.e.,
          variable definition)
ii. In the new row, double-click the cell in the Key column to make it editable
iii. Type the text found in the Key column of Table 14 - 1 , and press the Enter key
iv. Double-click the cell in the Value column to open the Value editor dialog (Figure 14 - 1 )

```
Figure 14 - 1 Value Editor Dialog
```
```
v. In the Value editor, type the text found in the Value column of Table 14 - 1 , and click OK
Key Value
fileOutboxPath /Training/outbox
filePrefix training_
listenerAddress 127.0.0.1
listenerPort 6661
Table 14 - 1 Configuration Map Variable Keys, Values
```

```
63 nextgen.com
```
```
d. Click Save in the Configuration Map menu to save the new Configuration Map variables
```
2. Update the channel created in Lab 3 to use these new Configuration Map variables
    a. Click Channels in the Mirth Connect menu to switch to Channels view
    b. In the listing of channels, select the channel named _Simple Channel - MLLP to File_ , and click Edit
       Channel in the Channel Tasks menu to edit the channel
       **Note:** If you named the channel differently when you created it in Lab 3, edit the channel with that
       name
    c. Edit the channel’s source connector settings
       i. Click the Source tab
ii. For the Local Address property in the Listener Settings section, select “Specific Interface”,
and replace the default address value of 0.0.0.0 with ${listenerAddress}
iii. For the Local Port property in the Listener Settings section, replace the existing port value of
6661 with ${listenerPort}
    d. Edit the channel’s destination connector settings
       i. Click the Destinations tab
ii. For the Directory property in the File Writer Settings, replace the existing directory path with
${fileOutboxPath}
iii. For the File Name property, update the existing file name to add the filePrefix variable to the
beginning of the name:
${filePrefix}${UUID}.txt
    e. Save the channel
    f. Deploy the channel
3. Just as you did in step 7 of Lab 3, send a message to the channel using HL7 Inspector (don’t forget to
    change HL7 Inspector’s destination port back to 6661, to match the port number defined by the
    Configuration Map variable)

**Results**
The results should be similar to what you saw when originally sending a message to the channel in Lab 3.
You should have not experienced any errors as a result of using the Configuration Map variables. Instead,
you should now see that:

- HL7 Inspector received an ACK message in response to the message sent
- The Received and Sent statistics displayed for the channel in the Administrator’s Dashboard should
    have each increased by one
- In the “/Training/outbox” folder, you should see a new file with a name consisting of “training_”,
    followed by a unique ID, followed by a .txt extension. The contents of this file should be the HL7
    message sent by HL7 Inspector.


```
64 nextgen.com
```
## Lab 15 Use Iterator Transformer to Build New Message with Repeating Data

**Objectives**
In this lab, you will create a new channel that will demonstrate the use of Iterator Transformer with Message
Builder steps to create a new outbound XML message from the inbound HL7 message. The channel will
have a Channel Reader source connector and one File Writer destination connector. The File Writer
destination will use an XML outbound message template and Message Builder steps to generate an XML
document file containing patient data from the inbound message. The transformer will have Message Builder
steps that are not part of an Iterator for the values from the non-repeating PID segment, as well as Message
Builder steps that are part of an Iterator for the values from the repeating NK1 segment.

**Figure 15 - 1 Iterator Transformer Channel Flow**

**Estimated Time to Complete**
15 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Verify that the status of the “Filter/Transformer Iterator dialog” setting on the Administrator tab of the
    Settings view (Figure 15 - 2 , below) is set to “Yes” (this setting was disabled in Step 4.e of Lab 4). If it is
    set to “No”, change it to “Yes” and then click on Save in the Administrator Tasks menu


```
65 nextgen.com
```
```
Figure 15 - 2 Filter/Transformer Iterator Dialog Setting
```
2. Create a new channel in the Default Group named _Iterator Transformer - Message Builder_
3. Leave the default source connector as a Channel Reader
4. On the Destination tab, configure the default destination as a File Writer that will generate an XML
    document file with patient data from the inbound HL7 message
    a. Rename the destination to XML Document (optional)
    b. Change the Connector Type to File Writer
    c. In the Directory field of the File Writer Settings section, type /Training/outbox
    d. Set the File Name field to a combination of the Channel ID and Message ID, followed by a .xml
       extension, so that it looks like:
       ${message.channelId}_${message.messageId}.xml
          i. Drag-and-drop the Channel ID mapping from the Destination Mappings list to the File Name
             field
ii. After the ${message.channelId} placeholder, type an underscore: _
iii. After the underscore, drag-and-drop the Message ID mapping from the Destination
Mappings list
iv. After the ${message.messageId} placeholder, type .xml
    e. For the Template field, write the encoded data that represents the new XML document using the
       built-in “pretty printer”
          i. Drag-and-drop the XML Pretty Printer mapping from the Destination Mappings list into the
             Template field
ii. Drag-and-drop the Encoded Data mapping from the Destination Mappings list into the
parentheses of the XML Pretty Printer mapping dragged over in the previous step
iii. The Template field for the XML Document destination should now look like this:
${XmlUtil.prettyPrint(${message.encodedData})}
5. Set the outbound template and create the non-iterating transformer steps to create the XML document
    a. Click Edit Transformer in the Channel Tasks menu
    b. Set the Inbound Message Template to “ADT-A03 - Hermes Conrad - Hospital A.hl7” in
       “/Training/Messages/HL7”
    c. Set the Outbound Message Template
       i. In the Data Type drop-down list for the Outbound Message Template, select XML
ii. Set the Outbound Message Template to “Patient Template with NoK.xml” in
“/Training/Messages/XML/Templates”

```
Set to “Yes”
```

```
66 nextgen.com
```
```
d. Click the Message Trees tab to view the message templates
e. For each entry in Table 15 - 1 (below), create a Message Builder step by dragging from the Inbound
Message Template Tree to the corresponding location in the Outbound Message Template Tree.
Each time you do this, the dialog shown below in Figure 15 - 3 will ask if you would like to add the
step to an Iterator. Click the No button (do not select the “Do not show this dialog again...” box).
```
```
Figure 15 - 3 Add Step to Iterator Dialog
```
```
Inbound Message Template Field (from) Outbound Message Template Field (to)
PID.2.1 (ID) patientId
PID.5.1 (Patient Name – Family Name) name – last
PID.5.2 (Patient Name – Given Name) name – first
PID.7.1 (Date/Time of Birth) dateOfBirth
PID.8.1 (Administrative Sex) gender
Table 15 - 1 Mappings from Inbound Message Template to Outbound Message Template
```
6. Create the Iterator step and Message Builder steps that will copy the repeating next-of-kin data
    a. For the entry in Table 15 - 2 , drag from the Inbound Message Template Tree to the corresponding
       location in the Outbound Message Template Tree, as shown below in Figure 15 - 4
       **Note:** The message used for the Inbound Message Template contains two NK1 segments. It does
       not matter which NK1 segment you choose to drag from.
          **Inbound Message Template Field (from) Outbound Message Template Field (to)**
          NK1.2.1 (Next of Kin – Family Name) nextOfKin - last
       **Table 15 - 2 First Next of Kin Mapping from Inbound Message Template to Outbound Message Template**


```
67 nextgen.com
```
```
Figure 15 - 4 Dragging from Inbound to Outbound Template
```
b. This time, when prompted to create an Iterator for the step by the dialog shown above Figure 15 - 3 ,
click Yes. This will display the Iterator Wizard dialog show below in Figure 15 - 5

```
Figure 15 - 5 Iterator Wizard
```

```
68 nextgen.com
```
```
c. In the Iterator Wizard, leave the iteration settings as their default values and click OK to create the
Iterator group step with the Message Builder for the mapping in Table 15 - 2 (above)
d. For each of the remaining next of kin values to map, as defined below in Table 15 - 3 , drag from the
Inbound Message Template Tree to the corresponding location in the Outbound Message Template
Tree.
Inbound Message Template Field (from) Outbound Message Template Field (to)
NK1.2.2 (Next of Kin – Given Name) nextOfKin – first
NK1.3.1 (Next of Kin – Relationship
Identifier)
```
```
nextOfKin – relationship
```
```
NK1.5.1 (Next of Kin – Phone Number) nextOfKin – phoneNumber
Table 15 - 3 Remaining Next of Kin Mappings from Inbound Message Template to Outbound Message
Template
```
```
e. When prompted once again to add the step to a new or existing Iterator, click Yes
f. You will now be prompted by the Iterator Wizard dialog to create a new Iterator, or choose an
existing iterator, as shown below in Figure 15 - 6. Leave the settings as their default values (Choose
Existing Iterator, For each msg[‘NK1’]), and click OK
```
```
Figure 15 - 6 Iterator Wizard - Choose Existing Iterator for NK1
```
```
g. Repeat steps 6.d through 6.f, above, for the remaining entries in Table 15 - 3
h. Your transformer list should now look like Figure 15 - 7 (below)
```
```
Figure 15 - 7 Transformer List with NK1 Iterator
```
```
i. Click Back to Channel in the Mirth Connect Views menu
```
7. Save the channel
8. Deploy the channel
9. Use the Dashboard’s Send Message feature to send the following messages to the channel:
    - ADT-A01 - Morgan Proctor - General Hospital.hl7
    - ADT-A03 - Hermes Conrad - Hospital A.hl7


```
69 nextgen.com
```
**Results**
On the Dashboard of the Administrator, the Received and Sent counts should each increase by one for each
message sent. In the “/Training/outbox” folder, you should see two new files. Each file should be named
with the ID of the channel, followed by and underscore, followed by the message ID, with a .xml extension.
For example, efd3af0e-17ce-489a-b59a-e0738af3cde8_1.xml

Each file should contain the XML document generated using the XML structure defined by the Outbound
Message Template and populated with the data from the HL7 message. In addition to the basic patient
demographic data populated from the PID segment, you should see a <nextOfKin> element, along with child
elements, for each NK1 segment in the original message. For example, if the HL7 message had three NK1
segments, the XML should have three <nextOfKin> elements, each populated with the data from an NK1
segment. An example of the expected output is shown below in Figure 15 - 8.

```
<patient>
<patientId>1234567</patientId>
<name>
<last>Proctor</last>
<first>Morgan</first>
</name>
<dateOfBirth>19650601</dateOfBirth>
<gender>F</gender>
<nextOfKin>
<last>Dunn</last>
<first>N.</first>
<relationship>FND</relationship>
<phoneNumber>(612) 554-7474</phoneNumber>
</nextOfKin>
<nextOfKin>
<last>Proctor</last>
<first>Ima</first>
<relationship>SIS</relationship>
<phoneNumber/>
</nextOfKin>
<nextOfKin>
<last>Proctor</last>
<first>Tress</first>
<relationship>SIS</relationship>
<phoneNumber>217- 555 - 2201</phoneNumber>
</nextOfKin>
</patient>
```
**Figure 15 - 8 Example XML Output**


```
70 nextgen.com
```
## Lab 16 Use Iterator Filter to Accept Messages with Condition in Repeating Segment

**Objectives**
In this lab, you will create a channel that uses an Iterator Filter on the source connector to only accept
messages where the patient is allergic to penicillin. Patient allergy information is specified in the AL1
segment, which is an optional repeating segment. Because it is a repeating segment, you will need to use
an Iterator Filter with a Rule Builder to iterate over all the AL1 segments, checking each one for a value of
“PENICILLIN” in AL1.3.2. Because the allergen text description contained in AL1.3.2 is not required to be in
a particular case, you will need to also use the JavaScript String function toUpperCase() to perform a case-
insensitive comparison.

**Figure 16 - 1 Iterator Filter Channel Flow**

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Create a new channel in the Default Group named _Iterator Filter - Rule Builder_
2. Configure the source connector as a TCP Listener (MLLP transmission mode)
    a. In the Listener Settings section, change the Local Port to 6668
3. Create the Iterator Filter in the source connector that only accepts messages if there exists at least one
    AL1 segment with an allergen text description of “PENICILLIN” in AL1.3.2
    a. Click Edit Filter in the Channel Tasks menu
    b. Set the Inbound Message Template on the Message Templates tab to the message in the file
       “ADT-A01 - Morgan Proctor - General Hospital.hl7”
    c. Click the Message Trees tab to view the message templates


```
71 nextgen.com
```
```
Find the AL1.3.2 node in the first AL1 node in the Inbound Message Template Tree, and drag and
drop it into the filter list area. This will display a dialog prompting for option to use Iterator (Figure
16 - 2 )
```
```
Figure 16 - 2 Prompt to Add Filter Rule to Iterator
```
d. Click Yes. This will display the Iterator Wizard dialog shown below in Figure 16 - 3

```
Figure 16 - 3 Iterator Wizard
```
e. In the Iterator Wizard, leave the iteration settings as their default values and click OK to create the
Iterator group with the Rule Builder for AL1.3.2
f. Edit the Rule Builder filter that was created so that it will accept if the value in AL1.3.2 equals
“PENICILLIN” (case-insensitive)
iii. In the Rule Builder that was created, edit the code in the Field property to convert the value
to all uppercase. The code should look like the following (the bolded part is the code to add):
msg['AL1'][i]['AL1. 3 ']['AL1. 3. 2 '].toString() **.toUpperCase()**
iv. Select the Equals radio button
v. Click the New button to add a new value to the Values list
vi. Double-click the value cell to make it editable
vii. Type "PENICILLIN" (quotes included) and click Enter
viii. The Rule Builder settings should now like Figure 16 - 4 (below)

```
Figure 16 - 4 Rule Builder Filter for AL1.3.2 in Iterator
```

```
72 nextgen.com
```
```
g. No changes are necessary for the Iterator itself. However, if you wish to verify the settings, click the
Iterator row in the filters list. The settings should appear as in Figure 16 - 5 (below)
```
```
Figure 16 - 5 Default Settings for Iterator
```
```
h. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel View
```
4. Configure the default destination connector to be a File Writer
    a. Change the Connector Type to File Writer
    b. Set Directory to /Training/outbox
    c. Set the File Name field to the Unique ID destination mapping, followed by a .txt extension:
       ${UUID}.txt
    d. Set the Template field to the Encoded Data destination mapping:
       ${message.encodedData}
5. Save the channel
6. Deploy the channel
7. Configure HL7 Inspector to send to the channel on port 666 8
8. Send the following messages to the channel using HL7 Inspector:
    - ADT-A0 1 - Colleen O’Hallahan - SHM.hl7
    - ADT-A01 - Morgan Proctor - General Hospital.hl7
    - ADT-A05 - Linda van Schoonhoven - Hospital C.hl7
    - ADT-A08 - Lars Fillmore - Hospital B.hl7

**Results**
After sending all four of the above HL7 message files, the Dashboard statistics for the channel should be 4
Received, 3 Filtered and 1 Sent. In HL7 Inspector, note that the acknowledgement code in the ACK
message returned for the Morgan Proctor message should be AA, while the others should have an
acknowledgement code of AR. This is because the other three were rejected.

Of the four messages sent, only the ADT-A01 for Morgan Proctor contained an AL1 segment where the
allergen was “PENICILLIN”. Therefore, when viewing messages in the Channel Messages view, this is the
only message that should have a status of “SENT” for the destination. The other three should have a status
of “FILTERED” on the source connector. Likewise, this is the only message that should have been written
out as a file to the “/Training/outbox” folder.


```
73 nextgen.com
```
## Lab 17 Use a JavaScript Transformer to Iterate over Repeating Segments and Build Lab Report

**Objectives**
In this lab, you will create a channel that uses a JavaScript transformer to create a lab report from repeating
segments in a lab observation message. The JavaScript transformer iterates over all segments in the
message and builds a JavaScript string from some of the values in the OBR and OBX segments. It then
places the resulting string variable into a Mapper variable. Finally, the File Writer destination connector
writes the lab report to a file.

**Figure 17 - 1 JavaScript Transformer Lab Processing Flow**

**Estimated Time to Complete**
15 - 20 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Create a new channel in the Default Group named _JavaScript Transformers - Lab Report_
2. Leave the source connector configured as a Channel Reader
3. Configure the default destination as a File Writer that will generate and write the lab report
    a. Rename the destination to Lab Report File
    b. Change the Connector Type to File Writer
    c. In the File Writer Settings section, specify the settings as shown below in Table 17 - 1 :
       **Setting Value**
       Directory /Training/outbox
       File Name LabReport_${message.messageId}.txt
          **Note:** You can drag-and-drop this value from the Message ID entry in the
          Destination Mappings list
       Template Leave blank for now (this will be set in Step 5 )
**Table 17 - 1 File Writer Settings**
4. Create a JavaScript transformer step to build the text for the lab report file
    **Note:** The final code created in this step can be found in Figure 17 - 3 on page 75


```
74 nextgen.com
```
a. Click Edit Transformer in the Channel Tasks menu
b. Click Add New Step in the Transformer Tasks menu
c. In the new row added to the transformer steps list, double-click the cell in the Type column and
select JavaScript from the drop-down menu (Figure 17 - 2 )

```
Figure 17 - 2 Selecting the JavaScript Transformer Type
```
d. Double-click the cell in the Name column to make it editable, and type Build Lab Report
(optional)
e. In the JavaScript editor, we will need a variable to hold the text for the lab report string. Add the
following line of code:
var labReportStr = "";

f. Next, add code to loop over each segment in the message
**Note:** You can get the code template for the loop by pressing Ctrl+Space, typing “iterate” (without
quotes), and then selecting the “Iterate Over All Segments” from the list. Then, simply modify the
code to match the code below.
for each (seg in msg.children())
{
}

g. Within the loop, your code will need to check to see if the segment in the current iteration is an OBR,
and if so, add a line to the report to show the order number:
if (seg.name().toString() == "OBR")
{
labReportStr += "Results for Order " +
seg['OBR.2']['OBR.2.1'].toString() + "\n";
}

h. Also within the loop, if the segment in the current iteration is not an OBR, add code to check to see if
it is an OBX, and if so, add a line to the lab report for the observation name (OBX.3.2), observation
value (OBX.5.1) and observation units (OBX.6.1):
else if (seg.name().toString() == "OBX")
{
labReportStr += seg['OBX.3']['OBX.3.2'].toString() + ": " +
seg['OBX.5']['OBX.5.1'].toString() + " " +
seg['OBX.6']['OBX.6.1'].toString() + "\n";
}


```
75 nextgen.com
```
```
i. Finally, after having iterated through all the message’s segments, you will need a line of code to add
the generated lab report string to the channel map so that it is available to the destination connector:
channelMap.put("labReport", labReportStr);
j. After entering the code in the previous steps, the final result for the JavaScript transformer step
should look like the code in Figure 17 - 3 below (comments optional):
```
```
// String to hold lab report text.
var labReportStr = "";
```
```
// Loop through all segments
for each (seg in msg.children())
{
// If OBR, output line with order number
if (seg.name().toString() == "OBR")
{
labReportStr += "Results for Order " +
seg['OBR.2']['OBR.2.1'].toString() + "\n";
}
// If OBX, output line with observation name, value and units
else if (seg.name().toString() == "OBX")
{
labReportStr += seg['OBX.3']['OBX.3.2'].toString() + ": " +
seg['OBX.5']['OBX.5.1'].toString() + " " +
seg['OBX.6']['OBX.6.1'].toString() + "\n";
}
}
```
```
// Put the report string in the channel map for use in the destination
// template.
channelMap.put("labReport", labReportStr);
```
```
Figure 17 - 3 Final Code for JavaScript Transformer to Create Lab Report
```
```
k. Click Back to Channel in the Mirth Connect Views menu
```
5. Set the output Template value for the Lab Report File destination to the labReport channel map variable
    created in the previous step by dragging that variable from the Destination Mappings list
6. Save the channel
7. Deploy the channel
8. Use the Dashboard’s Send Message feature to send the following message (which contains lab order
    results) to the channel:
    OUL-R21 - Leo Wong - ABC Diagnostics.hl7

**Results**
The Dashboard statistics for the channel should show 1 received and 1 sent. In the “/Training/outbox”
folder, you should see a new file with the message number and .txt extension containing the lab report
created in the JavaScript transformers. The contents of the file should be as follows:


```
76 nextgen.com
```
```
Results for Order 1035052
White blood cells: 33.0 *10E 9/L
TSH: 3.5 mU/L
Albumin: 20 g/L
Vitamin B12: 98 pg/L
```
**Figure 17 - 4 Output for Lab Report File**


```
77 nextgen.com
```
## Lab 18 Use a JavaScript Transformer to Iterate over Repeating Segments and Modify the Message

**Objectives**
In this lab, you will create a channel that uses a JavaScript transformer perform complex message
modification before passing the message onto the destination. The JavaScript transformer deletes the first
OBX segment found in the message, and then renumber the Set IDs of the remaining OBX segments.
Additionally, this transformer step will add and populate two new segments: an NTE (Note) segment after
the existing PID segment and a custom ZZZ segment at the end of the message.

**Figure 18 - 1 JavaScript Transformers Lab Processing Flow**

**Estimated Time to Complete**
15 - 20 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Configure HL7 Inspector to listen on the default port used by the TCP Sender (6660)
    a. Open HL7 Inspector if not already open
    b. Click the button on the toolbar with the downward-pointing green arrow to open the Message
       Receiver tab (Figure 18 - 2 ). Alternately, you can select Receive Messages from the Tools menu.

```
Figure 18 - 2 Button to Open HL7 Inspector's Message Receiver
```

```
78 nextgen.com
```
```
c. In the Message Receiver tab, click the “Setup network” button (second button from the right) (Figure
18 - 3 )
```
```
Figure 18 - 3 HL7 Inspector Setup Network Button
```
```
d. In the Receive Network Setup dialog that appears, type the port specified in the TCP Sender (6660),
and check the Reuse box (Figure 18 - 4 )
Note: You must check the Reuse box in this dialog. If this box is not checked, HL7 Inspector will not
return a response to your channel.
```
```
Figure 18 - 4 HL7 Inspector Receive Network Setup Dialog
```
```
e. Click OK to accept the changes
f. Click the “Start receiving message service” button (the button with the blue “play” triangle) to start
the receiver listening on port 6660 (Figure 18 - 5 ). The Message Receiver window should now
display the message:
Listening on port 6660
Note: Upon starting the Message Receiver, you may see a Windows dialog asking to allow access
to port 6660. If so, click the “Allow” button.
```
```
Figure 18 - 5 HL7 Inspector Start Receiving Message Service Button
```
2. Create a new channel in the Default Group named _JavaScript Transformers_
3. Leave the source connector configured as a Channel Reader


```
79 nextgen.com
```
4. Configure the default destination connector as a TCP Sender (MLLP transmission mode)
    a. Rename the destination connector to Alter and Forward Message (optional)
    b. Change the Connector Type to TCP Sender
    c. In the TCP Sender Settings section, verify that the Remote Port field value is set to 6660
5. Create a JavaScript transformer step to delete the first OBX segment, renumber the Set IDs for the
    remaining OBXs, and add NTE and ZZZ segments
    **Note:** The final code created in this step can be found in Figure 18 - 6 on page 80
    a. Click Edit Transformer in the Channel Tasks menu
    b. Click Add New Step in the Transformer Tasks menu
    c. In the new row added to the transformer steps list, double-click the cell in the Type column and
       select JavaScript from the drop-down menu
    d. Double-click the cell in the Name column to make it editable, and type Delete OBX and insert
       NTE (optional)
    e. In the JavaScript editor, add the code to delete the first OBX segment:
       delete msg['OBX'][0];
    f. Add the code to create a variable for the Set ID, initializing it to 1:
       var setId = 1;
    g. Add the code to iterate over all remaining OBX segments in the message to renumber each Set ID in
       OBX.1.1:
       for each (seg in msg..OBX)
       {
          seg['OBX.1']['OBX.1.1'] = setId++;
       }
    h. Next, after the loop, add code to add an NTE segment after the message’s PID segment:
       var noteSegment = createSegment('NTE');
       noteSegment['NTE.1']['NTE.1.1'] = 1;
       noteSegment['NTE.3']['NTE.3.1'] = "This is a note about the patient";
       msg['PID'] += noteSegment;
    i. Next, add code to add a custom ZZZ segment at the end of the message:
       var zzzSegment = createSegment('ZZZ', msg);
       zzzSegment['ZZZ.1']['ZZZ.1.1'] = "This is a custom Z segment";
    j. After completing the previous steps, your final code for the JavaScript transformer step should look
       like this (comments optional):


```
80 nextgen.com
```
```
// Delete the first OBX segment in the message.
delete msg['OBX'][0];
```
```
// Renumber the Set IDs of the remaining OBX segments.
var setId = 1;
for each (seg in msg..OBX)
{
seg['OBX.1']['OBX.1.1'] = setId++;
}
```
```
// Create an NTE segment, populate, and insert after PID segment.
var noteSegment = createSegment('NTE');
noteSegment['NTE.1']['NTE.1.1'] = 1;
noteSegment['NTE.3']['NTE.3.1'] = "This is a note about the patient";
msg['PID'] += noteSegment;
```
```
// Create a ZZZ segment, populate, and insert at the end of the message.
var zzzSegment = createSegment('ZZZ', msg);
zzzSegment['ZZZ.1']['ZZZ.1.1'] = "This is a custom Z segment";
```
```
Figure 18 - 6 Final Code for JavaScript Transformer to Delete Z Segments
```
```
k. Click Back to Channel in the Mirth Connect Views menu
```
6. Save the channel
7. Deploy the channel
8. Use the Dashboard’s Send Message feature to send the following message (which contains lab order
    results) to the channel:
    OUL-R21 - Leo Wong - ABC Diagnostics.hl7

**Results**
The Dashboard statistics for the channel should show 1 received and 1 sent.

In the HL7 Inspector’s Message Receiver window, you should see the message sent by the second
destination connector, Alter and Forward Message. Notice that after the PID segment there is now an NTE
segment:

NTE|1||This is a note about the patient

Additionally, you should now see a new ZZZ segment at the end of the message:

ZZZ|This is a custom Z segment

Also notice that the first OBX segment (for White blood cells) has been removed, and for the remaining OBX
segments, the Set IDs in OBX.1.1 have been correctly renumbered:

OBX| **1** |NM|2201^TSH||3.5|mU/L|0.27^4.20||||F|||20 1 70828203902||00017^BIOMAN...
OBX| **2** |NM|4024^Albumin||20|g/L|35^50||||F|||20 1 70828203848||00017^BIOMAN...
OBX| **3** |NM|1027^Vitamin B12||39|pmol/L|130^840||||F|||20 1 70828203904||00017^B...


```
81 nextgen.com
```
**Troubleshooting**

**Processing error on destination with error message “ConnectException: Connection refused:
connect”**

- HL7 Inspector’s Message Receiver is not started/listening. Start the message receiving service.
    See Step 1 on page 77.

**Processing error on destination with error message “Empty or blank response received”**

- HL7 Inspector is listening on port 6660, but the “Reuse” box was not checked when the message
    receiver was configured. Stop HL7 Inspector’s Message Receiver, and redo Step 1 on page 77 ,
    paying particular attention to Step 1.d.


```
82 nextgen.com
```
## Lab 19 Use Response Transformers to Process an HL7 Patient Query Response

**Objectives**
In this lab, you will create a channel that demonstrates how to use Response Transformer steps to extract
data from a response message returned by a destination system. The channel will have two destinations.
The first destination will send HL7 QRY-A19 (Patient Query) messages to a destination system via
TCP/MLLP. The destination system will then respond with an ADR-A19 response message. Depending on
the patient, the response message may or may not contain the patient demographic data that the query
requested. In the response transformer for that destination, you will create Mapper steps to extract data
from the response, including the acknowledgement code, query response status, and, potentially, patient
demographic data.

The second destination will be a File Writer that writes a simple patient report to a file, just like in Lab 5. The
report will include the demographic data extracted in the response transformer of the first destination. This
destination will also have a filter that checks the acknowledgement code and query response status, so that
the destination will only write the file if the response indicates that it found and returned the patient data.

**Figure 19 - 1 Response Transformers Patient Query Lab Flow**

**Estimated Time to Complete**
15 - 20 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer
- Any text editor, such as Notepad++


```
83 nextgen.com
```
**Step-By-Step**

1. Create a new channel in the Default Group named _Response Transformers - Patient Query_
2. Leave the source connector configured as a Channel Reader
3. Configure the default destination connector as a TCP Sender (MLLP transmission mode) that will send
    QRY-A19 messages to the destination system
    a. Rename the destination connector to Send Patient Query (optional)
    b. Change the Connector Type to TCP Sender
    c. In the Remote Address field of the TCP Sender Settings section, type the address for the destination
       system. s 1 a.mirthcorp.com or mirth.enterprisepreview.nextgen.com
    d. In the Remote Port field, type 9102
4. Create the response transformer steps to extract the required data from the response
    a. While still on the Destinations tab, click Edit Response in the Channel Tasks menu
    b. On the Message Templates tab, set the Inbound Message Template to the message in the file
       “ADR-A19 Template.hl7”, in the “/Training/Message/HL7/Templates” folder
    c. Click the Message Trees tab to view the Inbound Message Template Tree
    d. For each of the entries in Table 19 - 1 below, create a Mapper transformer step by finding the
       component in the Inbound Message Template Tree and dragging into the transformer list area, and
       then renaming the variable to the value in the “Rename Variable To” column
       **Note:** If the dialog appears asking to add the step to an iterator, select “No” for each step

```
HL7 Component Component Name Rename Variable To
MSA.1.1 Acknowledgement Code - Value acknowledgmentCode
QAK.2.1 Query Acknowledgement - Value queryResponseStatus
PID.2.1 Patient ID - ID Number patientId
PID.5.1 Patient Name - Family Name familyName
PID.5.2 Patient Name - Given Name givenName
PID.5.3 Patient Name – Second and Further... middleName
PID.7.1 Date/Time of Birth - Time dateOfBirth
PID.8.1 Administrative Sex - Value gender
Table 19 - 1 Mappings from HL7 Message to Mapper Variables
```
```
e. Click Back to Channel from the Mirth Connect Views menu
```
5. Create a new destination connector to write patient report file containing data from response, if found
    a. Click New Destination in the Channel Tasks menu
    b. Rename the new destination to Write Patient Report File (optional)
    c. Change the Connector Type to File Writer
    d. In the File Writer Settings section, specify the settings as shown below in Table 19 - 2 :
       **Setting Value**
       Directory /Training/outbox
       File Name ${patientId}_${message.messageId}.txt
          **Note:** You can drag-and-drop the message ID from the Message ID entry in
          the Destination Mappings list
       Template Leave blank for now
**Table 19 - 2 File Writer Settings**


```
84 nextgen.com
```
6. Create the filter rules for the File Writer destination so that it only writes the file if the query successfully
    returned patient data
    a. Click Edit Filter in the Channel Tasks menu
    b. Click Add New Rule in the Filter Tasks menu
    c. From the Available Variables section of the Reference tab, drag the variable named
       acknowledgementCode and drop into the Field property of the new Rule Builder, as shown in Figure
       19 - 2 below

```
Figure 19 - 2 Dragging from Available Variables into Field Property
```
```
d. For Condition, select Equals
e. Click the New button to add a new row to the Values table
f. Double-click the new row to make it editable, type “AA” (including quotes), and press the Enter key
g. The rule should now look like Figure 19 - 3 below
```
```
Figure 19 - 3 Rule Builder for Acknowledgement Code
```
```
h. Click Add New Rule in the Filter Tasks menu
```

```
85 nextgen.com
```
```
i. From the Available Variables section of the Reference tab, drag the variable named
queryResponseStatus and drop into the Field property of the new Rule Builder
j. For Condition, select Equals
k. Click the New button to add a new row to the Values table
l. Double-click the new row to make it editable, type “OK” (including quotes), and press the Enter key
m. Click Back to Channel in the Mirth Connect Views menu
```
7. Define the output template for the File Writer to generate the patient report (this is the same as was
    done in Lab 5)
    a. Open the file “Text Patient Report Template.txt” in the “/Training/Miscellaneous” folder and copy and
       paste the text into the File Writer’s Template field
    b. Drag the Formatted Date mapping from the Destination Mappings list to the end of the first line in the
       Template field (after “Patient Report - Created “)
    c. Change the value within the single quotes of the Formatted Date mapping that you just dragged over
       to MM/dd/yyyy (or whichever date format you choose)
       **Note:** For more information on date format patterns, see the Mirth Connect Programming Reference
    d. For each of the remaining fields in the template for the patient report, drag the corresponding
       mapping from the Destination Mappings list and drop it at the end of the line. For example, for
       “Patient ID: “, drag over the patientId mapping
    e. The Template field for the Patient Report destination should now look like this:
       Patient Report - Created ${date.get('MM/dd/yyyy')}
       -----------------------------------

```
Patient ID: ${patientId}
Last Name: ${familyName}
First Name: ${givenName}
Middle Name: ${middleName}
Date of Birth: ${dateOfBirth}
Gender: ${gender}
```
8. Save the channel
9. Deploy the channel
10. Send the following message to the channel using the Administrator’s Send Message tool:
    - QRY-A19 - Joseph Gilman - Hospital C.hl7
    - QRY-A19 - Morgan Proctor - General Hospital.hl7
    - QRY-A19 - Philip Fry - Omicron Clinic.hl7

**Results**
After sending the three QRY messages, the Dashboard statistics for the channel should show 3 Received, 1
Filtered, and 5 Sent. Expanding the channel to view the connector-level statistics, you should see that the
Send Patient Query destination shows all 3 messages were Sent, but the Writer Patient Report File
destination shows 1 Filtered and 2 Sent.

In the Channel Messages view, select the connector message for the Send Patient Query destination and
select the Response message on the Messages tab. This will allow you to see that the ADR-A19 response
message from the destination system. You can also see that the queries for patients Morgan Proctor and
Philip Fry returned demographic data, but the query for patient Joseph Gilman did not find any data. In each
response message, the QAK segment will have a value of “OK” in QAK.2, and the message will have PID
and PD1 segments containing the patient’s demographic data. However, if the query did not find data for


```
86 nextgen.com
```
the patient, the QAK segment will have a value of “NF” (not found) in QAK.2 and will not have a PID or PD1
segment.

In the “/Training/outbox” folder, you should see two new text files containing the patient reports generated
from the data in the query responses. One file contains the patient report for Morgan Proctor, while the
other contains the patient report for Philip Fry. Figure 19 - 4 below shows an example of one of the report
files.

```
Patient Report - Created 10/27/2020
-----------------------------------
```
```
Patient ID: 12345
Last Name: FRY
First Name: PHILIP
Middle Name: J
Date of Birth: 19711015
Gender: M
```
**Figure 19 - 4 Example Text Patient Report File Output**


```
87 nextgen.com
```
## Lab 20 Create Channels that Route Messages Using Channel Connectors

**Objectives**
In this lab, you will create two channels that will demonstrate routing messages between channels. The first
channel will act as the destination channel, using a Channel Reader as its source connector. The second
channel will receive messages using a TCP Listener, and then route messages to the destination channel
using a Channel Writer destination connector.

As part of the Channel Writer configuration, you will send Mapper variables to the destination channel as
metadata. The destination channel will then receive these values as Source Map variables.

As the two channels function together, you will create a channel group to hold both channels and deploy the
channels as a group.

**Figure 20 - 1 Routing Lab Processing Flow**

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector

**Step-By-Step**

1. Create a new channel group
    a. In the Channels view, verify that group mode is enabled by ensuring that the Groups button is
       selected in the bottom right-hand corner (Figure 20 - 2 ). You should also see “[Default Group]” at the
       top of the channels list.

```
Figure 20 - 2 Groups Button Selected in Channels View
```

```
88 nextgen.com
```
```
b. In the Group Tasks menu, click New Group. This displays the Channel Group Details dialog (Figure
20 - 3 )
```
```
Figure 20 - 3 Channel Group Details
```
```
c. In the Name field, replace the default group name with Routing Channels
d. Click the OK button to close the dialog and create the channel group
e. Click Save Group Changes in the Group Tasks menu
```
2. Create the destination channel with the Channel Reader in the Routing Channels group created in the
    previous step
    a. In the Channels view, click the Routing Channels group to select it
    b. Create a new channel by clicking New Channel in the Channel Tasks menu
    c. Name the new channel _Routing - Channel Reader_
    d. Configure the source connector as a Channel Reader that will return an auto-generated ACK
       i. Leave the Connector Type as Channel Reader
ii. In the Source Settings section, select “Auto-generate (Destinations completed)” from the
Response drop-down list
    e. Leave the destination connector configured as a Channel Writer without a destination channel
       selected
       **Note:** this will essentially be a “null” destination
    f. Save the channel
3. Create the channel with the Channel Writer in the Routing Channels group
    a. In the Channels view, click the Routing Channels group to select it
    b. Create a new channel by clicking New Channel in the Channel Tasks menu
    c. Name the new channel _Routing - Channel Writer_
    d. Configure the source connector as a TCP Listener (in MLLP transmission mode) that will return the
       response from the destination connector
          i. Select TCP Listener from the Connector Type drop-down list
ii. In the Listener Settings section, change the Local Port value to 6671
iii. In the Source Settings section, select “Destination 1” from the Response drop-down list
    e. Configure the destination connector as a Channel Writer
       i. Rename the destination to Write to Channel Reader Channel (optional)


```
89 nextgen.com
```
```
ii. In the drop-down list of channels to the right of the edit control for Channel Id, select “Routing
```
- Channel Reader”
**Note:** If you named the channel created in Step 2 differently than indicated in that step,
select that name
f. Add message metadata to the Channel Writer destination connector
i. To the right of Map Variable table for Message Metadata, click the New button to add a new
row
ii. Double-click the new row to make it editable
iii. Replace the default variable name (Variable 1) with localAddress
iv. Press the Enter key to save the variable
v. Repeat steps i through iv, above, this time adding the variable localPort
**Note:** For the message metadata variables defined above, the variable names _must_ be entered
exactly as shown, including case
Your settings for the Channel Writer should now look similar to those in Figure 20 - 4 , below

```
Figure 20 - 4 Channel Writer Settings
```
```
g. Save the channel
```
4. Deploy the channels in the Routing Channels group
    a. In the Channels view, click the Routing Channels group to select it
    b. Click Deploy Channel in the Channel Tasks menu
5. Using HL7 Inspector, send an HL7 message to the _Routing - Channel Writer_ channel on port 66 71

**Results**
In the Dashboard, the statistics for both the _Routing - Channel Writer_ and _Routing - Channel Reader_
channels should show 1 Received and 1 Sent.

In the Channel Messages view for the _Routing - Channel Writer_ channel, select the row for the destination
(optionally named “Write to Channel Reader Channel”), and then select the Response radio button. You
should see the HL7 ACK message generated by the _Routing - Channel Reader_ channel, along with a status
message indicating that the message was routed successfully.

In the Channel Message view for the _Routing - Channel Reader_ channel, select the Source row for the
message, which was sent from the _Routing - Channel Writer_ channel. On the Mappings tab, you should see
Source Map variables for sourceChannelId and sourceMessageId. These variables are created
automatically when receiving messages sent from a Channel Writer connector and indicate the ID of the


```
90 nextgen.com
```
channel from which the message was routed, and the ID of the message in that channel, respectively.
Additionally, you should see Source Map variables for localAddress and localPort. These values were
passed to the channel as message metadata from the Channel Writer.


```
91 nextgen.com
```
## Lab 21 Process an XML Batch File

**Objectives**
In this lab, you will create a channel that receives an XML batch that contains multiple patient records, with
each record delimited by the <patient> tag. The channel will process the batch so that each record in the
batch is processed as an individual message. You will then use a File Writer to write each individual
message to its own file, where each file name uses both the batchId and the batchSequenceId source map
variables.

**Figure 21 - 1 Process XML Batch File Lab Flow**

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer

**Step-By-Step**

1. Create a new channel named _Batch - XML_
2. Configure the data types and properties for processing an XML batch
    a. On the Summary tab of the Edit Channel view, click the Set Data Types button to open the Set Data
       Types dialog (Figure 21 - 2 )


```
92 nextgen.com
```
```
Figure 21 - 2 Set Data Types Dialog with Delimited Text Batch Settings
```
```
b. Select the Bulk Edit radio button at the top of the dialog
c. Select the “All” checkbox that appears
d. In the Inbound Properties section, select XML from the data type drop-down list
Note: you may need to scroll down in the list of data types to see XML
e. In the Batch section of the Inbound Properties, click the cell to the right of “Element Name” to make
that property editable
f. Type the following text for the “Element Name” property: patient
g. In the Outbound Properties section, select XML from the data type drop-down list
h. Click the OK button to close the dialog
```
3. Configure the source connector as a File Reader with batch processing enabled
    a. On the Source tab, select File Reader from the Connector Type drop-down list
    b. In the Source Settings section, select “Yes” for Process Batch (Figure 21 - 3 )

```
Figure 21 - 3 Process Batch Setting
```

```
93 nextgen.com
```
```
c. In the File Reader Settings section, specify the settings as shown below in Table 21 - 1 :
Setting Value
Directory /Training/inbox
Filename Filter Pattern *.xml
After Processing Action Delete
Table 21 - 1 File Reader Settings
```
4. Configure the default destination connector as a File Writer
    a. Rename the destination to Write Individual XML to File (optional)
    b. Change the Connector Type to File Writer
    c. In the File Writer Settings section, specify the settings as shown below in Table 21 - 2 :
       **Setting Value**
       Directory /Training/outbox
       File Name ${batchId}_${batchSequenceId}.xml
          **Note:** You will need to type these variable references into the File Name
          field. They are not available to drag-and-drop from the Destination
          Mappings list
       Template ${message.encodedData}
          **Note:** You can drag-and-drop this value from the Encoded Data entry in the
          Destination Mappings list
**Table 21 - 2 File Writer Settings**
5. Save the channel
6. Deploy the channel
7. Copy the “XML Batch.xml” file from the “/Training/Messages/XML” folder to the “/Training/inbox” folder

**Results**
Within a few seconds of copying the XML batch file to the inbox folder, the channel will process it, and the
file will be removed from the “/Training/inbox” folder. On the Dashboard, the statistics for the channel should
now show 6 Received and 6 Sent. In the Channel Messages view for the channel, you should see that a
message has been generated for each patient element in the XML batch file. Click on the Mappings tab in
the Channel Messages view. As you select different messages, you should see Source map variables for
batchComplete, batchId, and batchSequenceId. Assuming that you have only processed the batch once, all
six messages should have the same batchId value. The batchSequenceId variable should contain a
sequential value that increases from the first message to the last. Finally, all messages except for the last
should have a batchComplete value of false (the last message should have a value of true).

In the “/Training/outbox” folder, there should now be six new XML files created. The name for each file
should be in the format batchId_batchSequenceId.xml (for example, 1_1.xml, 1_2.xml, etc.). Each file
should contain the XML structure for an individual patient record, such as in Figure 21 - 4 , below.


```
94 nextgen.com
```
```
<patient>
<patientId> 100146 </patientId>
<name>
<last>O'Hallahan</last>
<first>Colleen</first>
<middle/>
<suffix/>
</name>
<dateOfBirth>19850704</dateOfBirth>
<gender>F</gender>
<address type="H">
<line1> 18 N ELM STREET</line1>
<line2/>
<city>NEWPORT BEACH</city>
<state>CA</state>
<postalCode>92660- 0518 </postalCode>
</address>
</patient>
```
**Figure 21 - 4 Example Patient Record XML File**

If you were to reprocess the batch file by copying it once again into the “/Training/inbox” folder, you would
see that you now have six new XML files in addition to the original six files. This time, however, the first
number in the file names will be six greater than the first six files (for example, 7_1.xml, 7_2.xml, etc.). This
is because the first number represents the batch ID, which is always the message ID of the first message in
the batch.

**Troubleshooting**

**Only one message is processed and only one file is written, containing the entire XML batch**

- Batch processing is not enabled in the source connector settings. See Step 3.b on page 92.

**XML batch file is read by File Reader (and removed from inbox folder), but no messages are
processed**

- Element Name property for splitting the batch as specified in the Set Data Types dialog is missing or
    invalid. See Steps 2.e and 2.f on page 92.

**All six messages were written to a single file, and the filename contains Velocity variable notation
(${...})**

- The variable references for the batch ID and/or batch sequence ID used in the filename are
    incorrect. Variable references must be typed exactly as specified, including correct case. See Step
    4.c on page 93.


```
95 nextgen.com
```
## Lab 22 Launch Command Line Interface, Execute Commands

**Objectives**
In this lab, you will use the Command Line Interface (CLI) to issue commands to the Mirth Connect Server,
such as to start and stop deployed channels.

**Estimated Time to Complete**
5 minutes

**Tools Used**

- Any text editor, such as Notepad++
- Windows Command Prompt
- Mirth Connect Administrator
- Command Line Interface (CLI)

**Step-By-Step**

1. If you have changed the login ID and/or password for the default Mirth Connect user, edit the “mirth-cli-
    config.properties” file to reflect those changes
    a. In the “conf” subfolder of the Mirth Connect installation folder, open the file “mirth-cli-
       config.properties” in a text editor such as Notepad++
    b. Update the entries for user and password to reflect the username and password of a valid Mirth
       Connect user
    c. Save the file
2. Open a Command Prompt window by clicking the Command Prompt icon in the Taskbar (or select All
    Programs > Accessories > Command Prompt from the Windows Start menu)

```
Figure 22 - 1 Command Prompt in Windows Taskbar
```
3. At the command prompt, change to the Mirth Connect installation directory (usually “\Program Files\Mirth
    Connect”). For example:
    cd "\Program Files\Mirth Connect"
    **Note:** This step is only necessary if you are doing the lab in your own environment. The PC supplied for
    your training class is already configured to open directly into the correct installation directory.
4. Type mccommand to execute the CLI
5. At the CLI $ prompt, type status to show the status of all deployed channels
6. Type channel stop * to stop all deployed channels
7. In the Administrator, notice that all channels are now stopped
8. Type channel start * to restart the deployed channels
9. In the Administrator, notice that all channels are now started
10. Issue whatever other commands you would like
11. When finished, typed quit to exit the shell client



nextgen.com

Section Two

Supplemental Labs



```
99 nextgen.com
```
## Lab 23 Add Custom Formatting to HL7 Data in Mappers

**Objectives**
In this lab, you will expand upon the channel created in Lab 5 to add formatting to the date of birth and
gender values for the output in the first destination. For the date of birth, you will change the format from the
standard HL7 format (e.g., 19411225) to a more human-readable format, such as the standard long U.S.
format (e.g., December 25, 1941), or the standard long European format (e.g., 25 December, 1941).

For the gender value, you will output the actual value that the gender code represents. For example, if the
PID.8.1 value is “M”, you will output “Male”, if it is “F”, you will output “Female”, etc.

**Estimated Time to Complete**
5 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Edit the channel that you created in Lab 5 by going to the Channels view, selecting the channel named
    _Transformers – Create Text Report_ , and then selecting Edit Channel from the Channel Tasks menu.
2. Edit the Transformer for the destination, Patient Report File
    a. Click the Destinations tab
    b. Select the Patient Report File destination in the destinations list if it is not already selected
    c. Click Edit Transformer in the Channel Tasks menu
3. Format the date of birth value using a Java function call
    a. Select the dateOfBirth Mapper variable in the transformer steps list
    b. Click the Reference tab next to the Message Trees and Message Templates tabs
    c. In the Category drop-down list, select Date Functions
       **Note:** Date Functions appears near the bottom of the list; you may need to scroll the list down to see
       it
    d. Select Convert Date String, and drag-and-drop it into the beginning of the Mapping field, placing it
       _before_ the value that is currently in that field. The contents of the Mapping field should now look like
       the following:
       var datestring = DateUtil.convertDate(inpattern, outpattern,
       date);msg['PID']['PID.7']['PID.7.1'].toString()
    e. Delete the var dateString = part of the inserted code, including the space that follows the
       equals sign
    f. Delete the date); part of the inserted code
    g. Add a closing parenthesis at the very end of the code
    h. Replace inpattern with "yyyyMMdd" (including the quotation marks)
    i. Replace outpattern with "MMMM dd, yyyy" (including the quotation marks). Alternatively, to
       output the date in the European format, replace outpattern with "dd MMMM, yyyy" (including
       the quotation marks)


```
100 nextgen.com
```
```
j. The code in the Mapping field should now look like:
DateUtil.convertDate("yyyyMMdd", "MMMM dd, yyyy",
msg['PID']['PID.7']['PID.7.1'].toString())
Or, if using the European date format, it should look like:
DateUtil.convertDate("yyyyMMdd", "dd MMMM, yyyy",
msg['PID']['PID.7']['PID.7.1'].toString())
```
4. Format the gender value using the Mapper’s String Replacement functionality
    a. Select the gender Mapper variable in the transformer steps list
    b. Click the New button to the right of the String Replacement list
    c. Double-click the cell in the Regular Expression column to make it editable
    d. Type "^(M|m)$" (including quotation marks) and press Enter to accept changes
    e. Double-click the cell in the Replace With column to make it editable
    f. Type "Male" (including quotation marks and press Enter to accept changes
    g. Repeat steps 4.b through 4.f, using instead the information from the following table:

```
Regular Expression Replace With
"^(F|f)$" "Female"
"^(O|o)$" "Other"
"^(U|u)$" "Unknown"
Table 23 - 1 String Replacement Values
```
```
Note: In the regular expressions listed above, the pipe, or vertical bar character separates alternate
choices, grouped within the parentheses. The carat character indicates that the pattern should only
be matched when found at the beginning of the string. The dollar sign character indicates that the
pattern should only be matched when found at the end of the string. By using them together, they
indicate that the replacement should only be performed when one of the characters within the
parenthesis (“M” or “m”, for example) is the only character found in the string.
```
5. Provide a default value for the gender Mapper variable (the value to use if PID.8.1 does not contain any
    value)
    a. While still in the Mapper step for gender, type “Unknown” (including quotation marks) in the Default
       Value field
6. Click Back to Channel in the Mirth Connect Views menu
7. Save the channel
8. Deploy the channel
9. Send an ADT message to the channel using the HL7 Inspector. This can be the same message that
    you sent before in Step 8 , or a different message.

**Results**
Just as before in Lab 5, for each message that you send to the channel, the Received count and Sent count
should each increase by one in the Dashboard. In the “/Training/outbox” folder, you should see one new
file. The file should have the ID of the patient specified in the PID segment of the message sent, one with a
txt extension and the other with an xml extension.

The patient report in the file should now show the Date of Birth and Gender values formatted as specified,
as opposed to the unformatted data straight from the message. An example of this file is below in Figure
23 - 1.


```
101 nextgen.com
```
```
Patient Report - Created 01/09/2012
-----------------------------------
```
```
Patient ID: 540091
Last Name: Panucci
First Name: John
Middle Name:
Date of Birth: March 14, 1949
Gender: Male
```
**Figure 23 - 1 Example Text Patient Report File Output with Formatted Date of Birth and Gender**


```
102 nextgen.com
```
## Lab 24 Install a New Database Driver for Use with the Database Reader/Writer Connectors

**Objectives**
In this lab, you will install database driver for a database called Advantage Database Server 8.1, for use with
the Database Reader and Database Writer connectors. This will involve placing the driver file in the correct
location in the Connect installation directory, as well as updating the database driver configuration file.

**Estimated Time to Complete**
5 minutes

**Tools Used**

- Connect Administrator
- Server Manager
- Windows Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Copy the file adsjdbc.jar from the “/Training/Jars” folder to the “custom-lib” folder of the Connect
    installation folder (usually “/Program Files/Mirth Connect”)
2. Add an entry for the new database driver to the dbdrivers.xml configuration file
    a. Open the file dbdrivers.xml in the “conf” folder of the installation folder for editing (your computer is
       installed with the Notepad++ editor, or you can use Notepad or WordPad)
    b. Add the following line after the last driver element in the XML document (this should all be on one
       line):
       <driver class="com.extendedsystems.jdbc.advantage.ADSDriver" name="Advantage
       Database Server 8.1" template=
       "jdbc:extendedsystems:advantage://host:port;catalog=path;TableType=type"
       selectLimit=""/>
       **Note:** The easiest way to add the above entry is to copy one of the existing driver entries and edit it
       so that it reflects what is shown above
    c. Save your changes
3. If the Administrator is currently running, close the application
    a. Click Logout from the Other menu
    b. In the Login window, click the Exit button
4. Restart the Mirth Connect Server


```
103 nextgen.com
```
```
a. Double-click the Mirth icon in the Windows notification area (system tray), as shown in Figure 24 - 1
below, to open the Server Manager
```
```
Figure 24 - 1 Server Manager Icon in Notification Area
```
```
b. In the Server Manager, click the Restart button
c. After a short while, a pop-up will appear indicating that the server has successfully restarted. Click
the OK button to proceed
```
5. In the Server Manager, click the Administrator button to re-launch the Administrator
6. Verify that Advantage Database Server 8.1 now appears as an option in the Driver drop-down list and
    that the Insert URL Template button works for both the Database Reader and Database Writer
    a. Create a new channel
    b. On the Source tab, change the connector type to Database Reader
    c. In the Driver drop-down list, verify that Advantage Database Server 8.1 appears at the end of the list
    d. Select Advantage Database Server 8.1 from the Driver list
    e. Click the Insert URL Template button. You should new see the URL template for the Advantage
       Database Server in the URL field
    f. On the Destinations tab, change the connector type to Database Writer
    g. In the Driver drop-down list, verify that Advantage Database Server 8.1 appears at the end of the list
    h. Select Advantage Database Server 8.1 from the Driver list
    i. Click the Insert URL Template button. You should new see the URL template for the Advantage
       Database Server in the URL field


```
104 nextgen.com
```
## Lab 25 Send Email with PDF Attachment Using SMTP Sender

**Objectives**
In this lab, you will extend the channel created in Lab 13 by cloning that channel, and then adding a new
SMTP Sender destination to it. You will then configure the new SMTP Sender destination to send an email
that contains patient data extracted from the inbound message, and also includes the PDF generated by the
Document Writer as an email attachment. You will also use an SMTP header to indicate the importance of
the email.

**Estimated Time to Complete**
10 - 12 minutes

**Tools Used**

- Mirth Connect Administrator
- Any web browser, or whichever application you use to access your email

**Step-By-Step**

1. Clone the channel created in Lab 13
    In the Channels view, select the channel that you created in Lab 13, _PDF Writer_
    a. Click Clone Channel in the Channel Tasks menu
    b. A dialog will appear, prompting you to provide a new name for the channel (Figure 25 - 1 ). Name the
       channel _PDF Writer with Email_

```
Figure 25 - 1 Prompt for New Name for Cloned Channel
```
```
c. Click the OK button to close the dialog and clone the channel
```
2. Add a new destination connector to the channel as an SMTP Sender
    a. On the Destinations tab, click New Destination in the Channel Tasks menu
    b. Rename the new destination to Send Email with PDF Attachment (optional)
    c. Change the Connector Type to SMTP Sender
3. Configure the SMTP Host settings for sending the email
    a. For the SMTP Host and SMTP Port settings, use the IP address and port, respectively, provided to
       you on your Student Information sheet
    b. For the Secure Connection, Use Authentication, Username and Password settings, use the values
       indicated on your Student Information sheet
4. Configure the to address, from address, and subject
    a. In the To field, enter your own email address or addresses. If specifying multiple address, separate
       each address with a comma
    b. In the From field, type email@mirthtraining.com
    c. In the Subject field, type Patient Report Generated


```
105 nextgen.com
```
5. Define the email body
    a. In the Body field, type the following text, inserting the proper destination mapping in place of FIRST,
       LAST, PID, TIME and DATE placeholders, as defined in Table 25 - 1 :
       Report generated for FIRST LAST (ID: PID) at TIME on DATE.
       Report PDF is attached.

```
Placeholder Destination Mapping Variable
FIRST firstName
LAST lastName
PID patientId
TIME Formatted Date (see step 5.b)
DATE Formatted Date (see step 5.c)
Table 25 - 1 Placeholders to Replace with Destination Mappings
```
```
b. For the first instance of the Formatted Date destination mapping, representing the time, update the
date/time pattern so that the variable looks like:
${date.get('HH:mm:ss')}
c. For the first instance of the Formatted Date destination mapping, representing the date, update the
date/time pattern so that the variable looks like:
${date.get('MM/dd/yyyy')}
Note: The above pattern is for the standard U.S. date format. You may instead choose to format the
date in whatever format you choose. For more information on date and time format patterns, see the
Mirth Connect Programming Reference.
d. The Body field for the email should now look like the following:
```
```
Report generated for ${firstName} ${lastName} (ID: ${patientId}) at
${date.get('HH:mm:ss')} on ${date.get('MM/dd/yyyy')}.
Report PDF is attached.
```
```
Figure 25 - 2 Final Email Body Text
```
6. Add the SMTP header to indicate the email is of high importance
    a. Click the New button to the right of the Headers list
    b. Double-click the cell in the Name column for the new entry to make it editable
    c. Delete the default value (Header 1), and type the value Importance in its place, and click the Enter
       key to accept your changes
    d. Double-click the cell in the Value column for the new entry to make it editable
    e. Type high and press the Enter key to accept your changes
7. Add the PDF created in the previous destination as an attachment, with its name in the format
    LAST_FIRST.pdf
    a. Click the New button to the right of the Attachments list
    b. Define the name of the attachment file
       i. Double-click the cell in the Name column for the new entry to make it editable
ii. Delete the default value (Attachment 1)
iii. Drag-and-drop the destination mapping for the patient’s last name into the cell in the Name
column


```
106 nextgen.com
```
```
iv. Type an underscore character
v. Drag-and-drop the destination mapping for the patient’s first name into the cell in the Name
column
vi. Type .pdf and press the Enter button to accept your changes
vii. The attachment name should now be:
${lastName}_${firstName}.pdf
c. Define the content for the attachment file
i. Double-click the cell in the Content column for the new entry to make it editable
ii. Drag-and-drop the destination mapping for the Document Writer’s response (Generate PDF)
into the cell in the Content column, and press the Enter key to accept your changes
iii. The attachment content should now be:
${d1.message}
d. Define the MIME type for the attachment file
i. Double-click the cell in the MIME Type column for the new entry to make it editable
ii. Type application/pdf and press the Enter key to accept your changes
e. The Attachments table should now look like Figure 25 - 3 , below
```
```
Figure 25 - 3 Attachments Settings for SMTP Sender
```
8. Save the channel
9. Deploy the channel
10. Use the Dashboard’s Send Message tool to send any ADT message to the channel

**Results**
The statistics in the Dashboard for the channel should show that 1 message was received and 2 messages
were sent. Check the email account which you specified as the To address in the SMTP Sender. Within a
short amount of time, you should receive the email generated by the SMTP Sender with a subject of “Patient
Report Generated”. In the body of the message, you should have the text specified in the SMTP Sender’s
Body field, with the placeholders replaced by the corresponding data from the message. For example:

```
Report generated for Amy Wong (ID: 111987 ) at 10:09:00 on 02/09/2015.
Report PDF is attached.
```
**Figure 25 - 4 Sample Email Body Text**

The email should also have the PDF generated by the Document Writer as an attachment. Open the
attachment to verify it can be viewed.

Finally, the email should be marked as having high importance. Note that how this is indicated depends
upon your email client. For example, Outlook indicates high importance with a red exclamation point next to
the subject. Gmail uses a yellow indicator next to the name of the sender.


```
107 nextgen.com
```
**Note:** If you don’t receive your email in a reasonable amount of time, check your email spam folder. If you
do not see the email there either, check to make sure that your SMTP settings are correct, and that the
SMTP Sender can successfully communicate with the SMTP host by clicking the “Send Test Email” button in
the SMTP Sender.


```
108 nextgen.com
```
## Lab 26 Use JavaScript Filter for Value in Repeating Segment

**Objectives**
In this lab, you will create a channel that uses a JavaScript filter on the source connector to only accept
messages where the patient is allergic to penicillin. Patient allergy information is specified in the AL1
segment, which is an optional repeating segment. Because it is a repeating segment, you will need to use a
JavaScript Filter to iterate over all of the AL1 segments, checking each one for a value of “PENICILLIN” in
AL1.3.2. Because the allergen text description contained in AL1.3.2 is not required to be in a particular
case, you will need to also use the JavaScript String method toUpperCase() to perform a case-insensitive
comparison.

This is the same functionality as in Lab 16, using a JavaScript filter in place of a Rule Builder within an
Iterator.

**Figure 26 - 1 JavaScript Filters Lab Flow Diagram**

**Estimated Time to Complete**
10 - 12 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Any text editor, such as Notepad++

**Step-By-Step**

1. Create a new channel in the Default Group named _JavaScript Filters_
2. Configure the source connector as a TCP Listener (MLLP transmission mode)
    a. In the Listener Settings section, change the Local Port to 6669
3. Create the JavaScript filter in the source connector that only accepts messages if there exists an AL1
    segment with an allergen text description of “PENICILLIN”
    a. Click Edit Filter in the Channel Tasks menu
    b. Click Add New Rule in the Filter Tasks menu
    c. For the new entry added to the filters list, double-click the cell in the Type column and select
       JavaScript from the drop-down list (Figure 26 - 2 )


```
109 nextgen.com
```
```
Figure 26 - 2 Selecting the JavaScript Filter Type
```
d. Write the JavaScript code to loop over only AL1 segments, checking the 3.2 field of any AL1
segment for the value “PENICILLIN”. The final code should look like the following (instructions to
create this code follow):

```
for each (seg in msg..AL1) {
var allergen = seg['AL1.3']['AL1.3.2'].toString();
if (allergen.toUpperCase() == "PENICILLIN")
{
return true;
}
}
```
```
return false;
```
```
Figure 26 - 3 Final Code for JavaScript Filter
```
```
i. From the Reference tab, drag over the “Iterate Over Segment” code template and drop it into
the JavaScript editor area
ii. In the part of the for each statement that defines over which collection of segments to iterate,
change the name of the segment to AL1 from the default value of SEG:
for each (seg in msg.. AL1 ) {
iii. In the body of the loop, replace the default name of the variable, sample_value, with
allergen:
var allergen = seg['SEG.1']['SEG.1.1'].toString();
iv. On the same line, edit the E4X code to get the value from AL1.3.2:
var allergen = seg[' AL1.3 '][ 'AL1.3.2 '].toString();
v. After the line to get the allergen value from AL1.3.2, add a new if statement to compare the
value to “PENICILLIN”, and return true if it matches:
if (allergen.toUpperCase() == "PENICILLIN") {
return true;
}
Note: The JavaScript editor’s code completion feature will automatically provide a list of
String methods after typing the period after the allergen variable. From this list, you can
select the toUpperCase() function, or you can manually type it. Also, the if statement’s
closing brace (}) will be automatically inserted after entering the opening brace ({)
```

```
110 nextgen.com
```
```
vi. Finally, after the closing brace of the for loop, add the following code to reject the message if
an AL1 segment with a 3.2 value equal to “PENICILLIN” was not found:
return false;
e. Click Back to Channel in the Mirth Connect Views menu
```
4. Configure the default destination connector to be a File Writer
    a. Change the Connector Type to File Writer
    b. Set Directory to /Training/outbox
    c. Set the File Name field to the Unique ID destination mapping, followed by a .txt extension:
       ${UUID}.txt
    d. Set the Template field to the Encoded Data destination mapping:
       ${message.encodedData}
5. Save the channel
6. Deploy the channel
7. Open and configure HL7 Inspector to send to the TCP Listener on port 666 9
8. Send the following messages to the channel using HL7 Inspector:
    - ADT-A0 1 - Colleen O’Hallahan - SHM.hl7
    - ADT-A01 - Morgan Proctor - General Hospital.hl7
    - ADT-A05 - Linda van Schoonhoven - Hospital C.hl7
    - ADT-A08 - Lars Fillmore - Hospital B.hl7

**Results**
After sending all four of the above HL7 message files, the Dashboard statistics for the channel should be 4
Received, 3 Filtered and 1 Sent. In HL7 Inspector, note that the acknowledgement code in the ACK
message returned for the Morgan Proctor message should be AA, while the others should have an
acknowledgement code of AR. This is because the other three were rejected.

Of the four messages sent, only the ADT-A01 for Morgan Proctor contained an AL1 segment where the
allergen was “PENICILLIN”. Therefore, when viewing messages in the Channel Messages view, this is the
only message that should have a status of “SENT” for the destination. The other three should have a status
of “FILTERED” on the source connector. Likewise, this is the only message that should have been written
out as a file to the “/Training/outbox” folder.


```
111 nextgen.com
```
## Lab 27 Create Global Deploy Script to Load Translation Table from Database

**Objectives**
In this lab, you will edit the global Deploy script to load a translation table for patients’ primary languages
from a database table. The database table defines the ISO 639-2 three-letter language codes commonly
used in HL7 messages, along with the names of the languages that the codes represent. You will load the
language code/name mappings from the database table into a map data structure, and then store that map
into a Global Map variable.

Then, you will modify an existing channel to add a Mapper transformer step to take the language code for
the patient from the inbound message, perform a lookup of the code in the language map, and store the
name of the language in the Mapper variable instead of the language code.

Table 27 - 1 , below, shows an example of some of the language code/name mappings that exist in the
Languages table.

```
Language Code Language Name
ABK Abkhaz
AAR Afar
AKA Akan
SQI Albanian
AMH Amharic
```
**Table 27 - 1 Example Rows in the Languages Database Table**

**Estimated Time to Complete**
15 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector
- Windows File Explorer
- Notepad++

**Step-By-Step**

1. Go to the global-level Deploy script
    a. If not already in Channels view, click Channels in the Mirth Connect menu
    b. Click Edit Global Scripts in the Channel Tasks menu
    c. In the Script drop-down menu at the top of the pane, select Deploy
2. Delete the existing default code
3. Insert the code to execute the query to get the data from the language translation table
    **Note:** You can view the final code for the Deploy Script in Figure 27 - 2 on page 113.
    a. From the Reference list at the right, drag over Perform Database Query and drop it into the
       JavaScript editor. The code in the deploy script editor should now look like this:


```
112 nextgen.com
```
```
var dbConn;
var result;
```
```
try {
dbConn = DatabaseConnectionFactory.createDatabaseConnection('driver',
'address', 'username', 'password');
result = dbConn.executeCachedQuery('expression');
} finally {
if (dbConn) {
dbConn.close();
}
}
```
```
Figure 27 - 1 Default Code for Querying a Database
```
```
b. In the call to DatabaseConnectionFactory.createdatabaseConnection(), delete the first
parameter, 'driver' (including the single-quotes)
c. In its place, drag over Postgres Driver from the Reference list (available in the Database Functions
category)
d. Replace the 'address' parameter with
'jdbc:postgresql://localhost:5432/mirthtraining'
e. Replace the 'username' parameter with 'mirthtraining'
f. Replace the 'password' parameter with 'mirthtraining'
g. On the next line of code, replace the 'expression' parameter with 'SELECT * FROM
Languages'
```
4. Insert the code to create a Java HashMap to store the language code translations
    a. Within the try block, but _before_ the call to
       DatabaseConnectionFactory.createdatabaseConnection(), insert a new line and type
       the following code:
       var languageMap = new Packages.java.util.HashMap();
5. Insert the code to loop over the results and add the language code/name mappings to the
    languageMap HashMap created in Step 4.a
    a. After the line with the call to dbConn.executeCachedQuery(), add the following code to loop
       over the results:
       while (result.next())
       {
       languageMap.put(result.getString(1), result.getString(2));
       }
6. Add the code to store the languageMap HashMap as a Global Map variable
    a. Insert a new line after the closing brace of the while loop created in Step 5.a
    b. On the new line, drag over the Put Global Variable Map template from the Reference list (available
       in the Map Functions category) to add the code to add a global variable
    c. In the call to globalMap.put(), replace the first parameter, key, with languageMap (leaving the
       quotes around languageMap)


```
113 nextgen.com
```
```
d. In the call to globalMap.put(), replace the second parameter, 'value' ( including the single-
quotes), with languageMap
e. Add a semicolon to the end of the call to globalMap.put()
The Deploy script code should now look like this:
```
```
var dbConn;
var result;
```
```
try {
var languageMap = new Packages.java.util.HashMap();
```
```
dbConn = DatabaseConnectionFactory.createDatabaseConnection(
"org.postgresql.Driver", 'jdbc:postgresql://localhost:5432/mirthtraining',
'mirthtraining', 'mirthtraining');
result = dbConn.executeCachedQuery('SELECT * FROM Languages');
```
```
while (result.next())
{
languageMap.put(result.getString(1), result.getString(2));
}
```
```
globalMap.put("languageMap", languageMap);
} finally {
if (dbConn) {
dbConn.close();
}
}
```
```
Figure 27 - 2 Final Code for Global Deploy Script
```
7. Save the script by clicking Save Scripts in the Script Tasks menu
8. Modify the channel created in Lab 5 to add a new Mapper variable that will use the new languageMap
    Global Map variable
    a. Edit the channel named _Transformers – Create Text Report_
       **Note:** This is the name of the channel as specified in Lab 5. If you named your channel differently,
       edit the channel with that name
    b. In the transformer for the Patient Report File destination connector, add a new Mapper transformer
       that will use the languageMap Global Map variable
          i. With the Patient Report File destination connector selected, click Edit Transformer in the
             Channel Tasks menu
ii. Create a new Mapper transformer for PID.15.1 by dragging from the Inbound Message
Template Tree into the transformers list area
iii. Rename the Variable to primaryLanguage
iv. Modify the value in the Mapping field so that it matches the following:
       globalMap.get('languageMap').get(msg['PID']['PID.15']['PID.15.1'].toString())
          **Note:** You can get the call to globalMap.get() from the Reference list as the code template
          Get Global Variable Map (in the Map Functions category)


```
114 nextgen.com
```
```
v. In the Default Value field, type "Not Specified" (including quotes)
vi. Click Back to Channel in the Mirth Connect Views menu
c. Modify the Template of the File Writer to use the new primaryLanguage variable
i. Following the last line in the File Writer’s Template, add a new label:
Primary Language:
ii. From the Destination Mappings list, drag over the primaryLanguage variable, and drop it
after the label added in the previous step
iii. The File Writer’s Template should now look like this:
Patient Report - Created ${date.get('MM/dd/yyyy')}
-----------------------------------
```
```
Patient ID: ${patientId}
Last Name: ${lastName}
First Name: ${firstName}
Middle Name: ${middleName}
Date of Birth: ${dateOfBirth}
Gender: ${gender}
Primary Language: ${primaryLanguage}
```
9. Save and deploy the channel
10. Send the following messages to the channel, using either the Dashboard’s Send Message tool, or by
    using HL7 Inspector sending to port 6663:
    - ADT-A08 - John Panucci - Sacred Heart.hl7
    - ADT-A01 - Colleen O'Hallahan - SHM.hl7

**Results**
After sending the two messages. In the “/Training/outbox” folder, you should now see two new files with .txt
extensions (in addition to two new files with .xml extensions). By viewing the contents of each file, you
should see each file contains a text report for the patient data similar to what you created in Lab 5.
However, each report now also contains a line for Primary Language. For the report for patient John
Panucci, the indicated language should be English. For the report for patient Colleen O’Hallahan, the
language should indicate “Not Specified”, as the PID.15.1 segment in that message did not contain a value.

Additionally, you can see the contents of the langaugeMap Global Map variable in the Administrator. In the
bottom pane of the Dashboard, click the Global Maps tab. Here, you can see an entry for the langaugeMap
variable (Figure 27 - 3 ).

**Figure 27 - 3 Dashboard's Global Maps Tab**

Notice, however, that you cannot see all of the values for the languageMap variable from this view. Double-
click the row for the languageMap variable to view the entire value. This opens the Mapping Value window


```
115 nextgen.com
```
(Figure 27 - 4 ). In this window, you can scroll through the entire value of the variable to verify that the values
were loaded correctly.

**Figure 27 - 4 Mapping Value Details**


```
116 nextgen.com
```
## Lab 28 Use a Postprocessor Script to Generate an ACK from a Destination that Uses Queuing

**Objectives**
This lab demonstrates one possible use of generating a response using the Postprocessor script. In this
case, the sending channel is using the Attempt First queuing option on its TCP Sender destination
connector. We want to respond from the destination’s ACK response, if possible. However, if the
destination application is unreachable (connection refused, for example), the message will be queued.
When a message is queued, the destination connector will not have an ACK message that the source
connector can use for its response. In that case, a custom-generated response will be required.

In this lab, you will create two separate channels—one that acts as the destination application, and one that
acts as the sending application with the queue on its destination. The destination channel will have a TCP
Listener that returns an auto-generated ACK with a text message in MSA.3.1 that indicates it was processed
by that channel.

For the sending channel, it will use a TCP Listener for its source connector, and a TCP Sender for its
destination connector. The TCP Sender will use the Attempt First queuing option, which will attempt to send
the message one time to the destination. If it is unable to send, it will then queue the message.

You will then need to write a Postprocessor script to determine if the destination was able to successfully
send the message, or if the message was queued. If the message was sent, the channel will use as its
response the response returned from the destination. Otherwise, if the message was queued, you will need
to generate a custom acknowledgement, and use it as the channel’s response.

**Figure 28 - 1 Custom Response with Queuing Lab Flow**

**Estimated Time to Complete**
10 - 15 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector

**Step-By-Step**

1. Create the receiving channel that acts as the destination
    a. Create a new channel named _Destination for Queuing Channel_
    b. Customize the successful text message for the auto-generated ACK response


```
117 nextgen.com
```
```
i. On the Source tab, click the Set Data Types button to open the Set Data Types dialog
ii. In the Response Generation section of the Inbound Properties, find the Successful ACK
Message property (Figure 28 - 2 ) and click the cell for it to make it editable
```
```
Figure 28 - 2 Set Data Types – Custom Successful ACK Message Setting
```
```
iii. Type Successfully processed by Destination for Queuing Channel
iv. Click OK to save the change
c. Configure the source connector as a TCP Listener (MLLP transmission mode)
i. Change the Connector Type to TCP Listener
ii. In the Listener Settings section, change the Local Port to 6673
d. Save the channel
e. Deploy the channel
```
2. Create the sending channel
    a. Create a new channel named _Custom Response with Queuing_
    b. Configure the source connector as a TCP Listener (MLLP transmission mode)
       i. Change the Connector Type to TCP Listener
ii. In the Listener Settings section, change the Local Port to 6672
iii. In the Source Settings section, select Postprocessor from the Response drop-down list
    c. Configure the destination connector as a TCP Sender (MLLP transmission mode) with queuing
       enabled
          i. Change the Connector Type to TCP Sender
ii. In the Destination Settings section, change Queue Messages to “On Failure”
iii. In the TCP Sender Settings section, change the Remote Port to 6673
3. Write the Postprocessor script to handle the destination’s response
    a. On the Scripts tab, select Postprocessor from the Script drop-down list
    b. Delete the default Postprocessor script code


```
118 nextgen.com
```
c. In the JavaScript editor, first write the code to get the destination’s response:

var responseD1 = responseMap.get('d1');
**Note:** You can get the call to responseMap.get() from the “Get Response Variable Map” code
template (Map Functions category)
d. Next, add the code to return the response from the destination if it has a status of SENT:

```
if (responseD1.getStatus() == "SENT")
{
return responseD1;
}
```
e. Next, add the code to generate and return a custom ACK if the message has a status of QUEUED:

else if (responseD1.getStatus() == "QUEUED")
{
var customACK = ACKGenerator.generateAckResponse(
message.getConnectorMessages().get(0).getRawData(),
"AA", "Message queued on destination");
return ResponseFactory.getSentResponse(customACK);
}
**Note:** You can get the call to ResponseFactory.getErrorResponse() from the “Create Sent
Response” code template (Map Functions category)
f. Finally, add the code to generate and return a custom ACK if there was an error during processing:

else
{
var customACK = ACKGenerator.generateAckResponse(
message.getConnectorMessages().get(0).getRawData(),
"AE", "An error occurred during processing");
return ResponseFactory.getErrorResponse(customACK);
}
**Note:** You can get the call to ResponseFactory.getErrorResponse() from the “Create Error
Response” code template (Map Functions category)
g. The final Postprocessor script code, in its entirety, should look like the code below in Figure 28 - 3 :


```
119 nextgen.com
```
```
var responseD1 = responseMap.get('d1');
```
```
if (responseD1.getStatus() == "SENT")
{
return responseD1;
}
else if (responseD1.getStatus() == "QUEUED")
{
var customACK = ACKGenerator.generateAckResponse(
message.getConnectorMessages().get(0).getRawData(),
"AA", "Message queued on destination");
return ResponseFactory.getSentResponse(customACK);
}
else
{
var customACK = ACKGenerator.generateAckResponse(
message.getConnectorMessages().get(0).getRawData(),
"AE", "An error occurred during processing");
return ResponseFactory.getErrorResponse(customACK);
}
```
```
Figure 28 - 3 Final Code for Postprocessor Script
```
4. Save the channel
5. Deploy the channel
6. Test the channel by sending a message to it first with _Destination for Queuing Channel_ started, then
    again with it stopped
    a. Configure HL7 Inspector to send to the _Custom Response with Queuing_ channel on port 667 2
    b. Send any HL7 message using HL7 Inspector
    c. Stop _Destination for Queuing Channel_
       i. On the Administrator’s Dashboard, select _Destination for Queuing Channel_
ii. In the Dashboard Tasks menu, click Stop
    d. Once again send any HL7 message using HL7 Inspector

**Results**
The Dashboard statistics for the _Custom Response with Queuing_ channel should show 2 Received, 1
Queued, and 1 Sent. For the _Destination for Queuing Channel_ , the statistics should show 1 Received and 1
Sent.

In HL7 Inspector, you should see the ACK messages received for each of the messages sent. For the ACK
message for the first message (sent while the destination channel was started), notice that the text message
in MSA.3.1 is “Successfully processed by Destination for Queuing Channel”. However, for the ACK
message for the second message, the text message in MSA.3.1 is “Message queued on destination”.

If you look at the message data in the Channel Messages view for the _Custom Response with Queuing_
channel and select the message row for the destination that has a status of SENT, you can see that the
Response on the Messages tab is the same as what was ultimately returned to the HL7 Inspector.
However, the destination that has a status of QUEUED does not have a response message.


```
120 nextgen.com
```
## Lab 29 Modify a Destination’s Response Using Response Transformers

**Objectives**
In this lab, you will create two channels that demonstrate how to modify the response from a destination
using Response Transformers. First, you will create a receiving channel that only accepts ADT-A01
messages. This channel will return an auto-generated ACK after the source transformer has executed. This
means that if it receives a message type other than ADT-A01, the message will be rejected, and the ACK
will contain “AR” for its acknowledgement code (MSA.1.1).

Next, you will create a sending channel that receives a message over MLLP from the HL7 Inspector. It then
sends the message to the receiving channel, and receives the ACK from that channel in response. You will
then use a Response Transformer to get the acknowledgement code from the ACK, and if it contains “AR”,
change it to “AA”. Finally, the modified ACK is returned to the HL7 Inspector.

**Figure 29 - 1 Response Transformer Lab Processing Flow**

**Estimated Time to Complete**
15 minutes

**Tools Used**

- Mirth Connect Administrator
- HL7 Inspector

**Step-By-Step**

1. Create the receiving channel
    a. Create a new channel in the Default Group named _Response Transformers - Receive ADT-A0 1_


```
121 nextgen.com
```
```
b. Configure the source connector as a TCP Listener (in MLLP transmission mode) that will return an
auto-generated ACK
i. Select TCP Listener from the Connector Type drop-down list
ii. In the Listener Settings section, change the Local Port value to 9101
iii. In the Source Settings section, verify that the Response selection is set to “Auto-generate
(After source transformer)” (this is the default setting)
```
2. Add filter rules to the source connector to only accept ADT-A01 messages
    a. While still on the Source tab, click Edit Filter in the Channel Tasks menu
    b. On the Message Templates, set the Inbound Message Template to any HL7 ADT message
    c. Click the Message Trees tab to view the Inbound Message Template Tree
    d. Create a Rule Builder filter that accepts the message if MSH.9.1 equals “ADT”
       i. In the Inbound Message Template Tree, expand the tree to find the MSH.9.1 component
          (with the green dot)
ii. Drag and drop this node into the filter rule list area
iii. For the Condition setting in the rule that is created, select “Equals”
iv. Click the New button to add a new value to the Values list
v. Double-click the value cell to make it editable
vi. Type "ADT" (quotes included) and press Enter
    e. Create a Rule Builder filter that accepts the message if MSH.9.2 equals “A01”
       i. In the Inbound Message Template Tree, expand the tree to find the MSH.9.2 component
          (with the green dot)
ii. Drag and drop this node into the filter rule list area
iii. For the Condition setting in the rule that is created, select “Equals”
iv. Click the New button to add a new value to the Values list
v. Double-click the value cell to make it editable
vi. Type "A01" (quotes included) and press Enter
    f. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel view
3. Leave the destination connector as the default Channel Writer with null destination
4. Save and deploy the channel
5. Create the sending channel with the Response Transformer
    a. Create a new channel in the Default Group named _Response Transformers - Modify Response_
    b. Configure the source connector as a TCP Listener (in MLLP transmission mode) that will return the
       response from the destination connector
          i. Select TCP Listener from the Connector Type drop-down list
ii. In the Listener Settings section, change the Local Port value to 6670
iii. In the Source Settings section, select “Destination 1” from the Response drop-down list
    c. Configure the default destination connector as a TCP Sender (MLLP transmission mode)
       i. Change the Connector Type to TCP Sender
ii. In the TCP Sender Settings section, change the Remote Port value to 9101
6. Modify the response from the destination using the destination connector’s Response Transformer
    a. While still on the Destinations tab with Destination 1 selected, click Edit Response in the Channel
       Tasks menu
    b. On the Message Templates tab, set the Inbound Message Template to the message in the file “ACK
       Template.hl7”, in the “/Training/Message/HL7/Templates” folder
    c. Click the Message Trees tab to view the Inbound Message Template Tree


```
122 nextgen.com
```
```
d. Create a Mapper transformer step for MSA.1.1 (acknowledgement code)
i. Drag the node for MSA.1.1 in the Inbound Message Template Tree into the transformer list
area to create the Mapper step
ii. Rename the variable to ackCode
e. Create a Message Builder transformer step to overwrite MSA.1.1 if the acknowledgement code is
“AR”
i. In the Inbound Message Template Tree, right click on the MSA.1.1 node (the green dot), and
select Map to Message from the context menu
ii. Click the Reference tab
iii. In the Available Variables pane, drag the ackCode variable into the Mapping field of the
Message Builder step
iv. Add a new entry into String Replacement table by clicking the New button to the right of the
table
v. Double-click the cell in the Regular Expression column to make it editable, and type “AR”
vi. Double-click the cell in the Replace With column to make it editable, and type “AA”
vii. Press the Enter key to save your changes
f. Create a JavaScript transformer step that will change the status of the response from ERROR to
SENT if the acknowledgement code was “AR”
Note: The final code for the step is in Figure 29 - 2 (below)
i. In the Transformer Tasks menu, click Add New Step
ii. Double-click the cell in the Type column, and select JavaScript
iii. In the JavaScript editor, type the following code:
if (
iv. Drag the ackCode variable from the Reference tab, and drop it after the opening parenthesis,
as follows:
if ( $('ackCode')
v. Complete the if condition so that looks like the following:
if ($('ackCode' ) == "AR")
vi. Add a newline to the code by pressing the Enter key with the cursor at the end of the line
vii. On the Reference tab, select Response Transformer from the Category list
viii. Drag the “Set Response Status to SENT” code template into the JavaScript editor
ix. Your code should now look like this:
```
```
if ($('ackCode') == "AR")
responseStatus = SENT;
```
```
Figure 29 - 2 Final code for JavaScript Transformer Step
```
```
g. Click Back to Channel from the Mirth Connect Views menu
```
7. Save and deploy the channel.
8. Using HL7 Inspector, send the following two HL7 messages to the _Response Transformer - Sender_
    channel on port 66 70 :
    - ADT-A01 - Morgan Proctor - General Hospital.hl7
    - ADT-A08 - Lars Fillmore - Hospital B.hl7


```
123 nextgen.com
```
**Results**
After sending the two HL7 messages, the Dashboard statistics for the _Response Transformer - Modify
Response_ channel should be 2 Received and 2 Sent. For the _Response Transformer - Receive ADT-A01_
channel, the statistics should be 2 Received, 1 Filtered, and 1 Sent.

In the HL7 Inspector, note that the acknowledgement code (MSA.1.1) is AA for both ACK messages
returned.

In the Channel Messages view for the _Response Transformer - Modify Response_ channel, you should see
that the Status of Destination 1 for both messages is SENT. However, in the Error column for the second
message, you should see that there was a Processing error.

Select the connector message row for Destination 1 of the second message to view the message content.
On the Messages tab, select the Response radio button. Notice that the Status is “ERROR: NACK sent
from receiver. (Rejected) Message Rejected.”, and in the Response message itself, the first field of the MSA
segment (the acknowledgement code) is AR.

Next, select the Processed Response radio button to view the version of the response message after it was
modified by the response transformer. Notice that the Status is now “ **SENT** : NACK sent from receiver.
(Rejected) Message Rejected.”, and the first field of the MSA segment shows an acknowledgement code of
AA.

Finally, if you select the Response for the source connector message, you should see that the response
data is the same as the Processed Response for Destination 1. This is the response that was returned to
the HL7 Inspector.


```
124 nextgen.com
```
## Lab 30 Process a CSV Batch, Write Results to Database

**Objectives**
In this lab, you will create a channel that receives a delimited text batch that contains multiple records in
comma-separated value (CSV) format. The channel will process the batch so that each record in the batch
is processed as an individual message. You will then use Mapper transformer steps to extract all of the
values from each record. Finally, you will configure a Database Writer destination connector to insert the
values from each record into a new row in a database table.

**Estimated Time to Complete**
15 minutes

**Tools Used**

- Mirth Connect Administrator
- SQuirreL SQL Client

**Step-By-Step**

1. Create a new channel named _Batch - Delimited Text to Database_
2. Configure the data types and properties for processing a delimited text batch
    a. On the Summary tab of the Edit Channel view, click the Set Data Types button to open the Set Data
       Types dialog (Figure 30 - 1 )

```
Figure 30 - 1 Set Data Types Dialog with Delimited Text Batch Settings
```
```
b. Select the Bulk Edit radio button at the top of the dialog
c. Select the “All” checkbox that appears
d. In the Inbound Properties section, select Delimited Text from the data type drop-down list
Note: you may need to scroll up in the list of data types to see Delimited Text
```

```
125 nextgen.com
```
```
e. In the Outbound Properties section, select Delimited Text from the data type drop-down list
f. Select the Single Edit ratio button at the top of the dialog
g. In the Serialization section of the Inbound Properties, click the cell to the right of Column Names to
make that property editable
h. Type the following text for the “Column Names” property (as if it appears on a single line):
PatientID,LastName,FirstName,MiddleInit,DOB,Gender,Address1,
Address2,City,State,PostalCode
Note: Alternatively, you can copy the above text from the first line of the file
“/Training/Messages/Delimited Text/Patients.csv”, and paste it into the “Column Names” field
i. In the Batch section of the Inbound Properties, change the value of the “Number of Header Records”
property from 0 to 1
j. Click the OK button to close the dialog
```
3. Configure the batch processing settings for the source connector
    a. On the Source tab, leave the Connector Type as a Channel Reader
    b. In the Source Settings section, select “Yes” for Process Batch (Figure 30 - 2 )

```
Figure 30 - 2 Process Batch Setting
```
4. Create Mapper variables for the column data in each record
    a. Click Edit Transformer to edit the source transformer
    b. For the Inbound Message Template, type the following text (all on a single line):
       PatientID,LastName,FirstName,MiddleInit,DOB,Gender,Address1,
       Address2,City,State,PostalCode
       **Note:** This is the same text entered in Step 2.h. So alternatively, you can copy the above text from
       the “Column Names” inbound property, or from the first line of the file
       “/Training/Messages/Delimited Text/Patients.csv”
    c. On the Message Trees tab, right-click on the “row” node and select Expand from the context menu
    d. For each and every value in the tree (PatientID, LastName, FirstName, etc.), create a Mapper
       transformer step by dragging the value from the Inbound Message Template Tree into the
       transformer list area. This should produce a total of 11 Mapper steps (numbered 0-10)
5. Configure the default destination connector as a Database Writer
    a. Rename the destination to Write Patient Data to Database (optional)
    b. Change the Connector Type to Database Writer
    c. In the Driver drop-down list of the Database Writer Settings section, select PostgreSQL
    d. Click the Insert URL Template button
    e. In the URL field, edit the URL template so that it matches the following:
       jdbc:postgresql://localhost:5432/mirthtraining
    f. In the Username field, type mirthtraining
    g. In the Password field, type mirthtraining
6. Generate the SQL statement to insert the patient data into the database table


```
126 nextgen.com
```
a. Click the Insert button above the SQL editor on the right-hand side. This opens the SQL Creation
dialog (Figure 30 - 3 )
b. In the “Filter by” field of the SQL Creation dialog, type patients (optional)
c. Click the Get Tables button to get the table metadata

```
Figure 30 - 3 The SQL Creation Dialog (Patients Table)
```
d. Select all of the columns in the Patients table, _except_ “seqid”, “dateadded”, and “datemodified”, by
checking the box to the left of each column name. Alternatively, you could check the box to the left
of “patients” (the table name), and then uncheck the “seqid”, “dateadded”, and “datemodified”
columns.
e. Click the Generate button. In the SQL editor, you should now see the following incomplete SQL
code ( **Note:** The code here may look slightly different due to text wrapping):

```
INSERT INTO patients (patientid, lastname, firstname, middlename,
dateofbirth, gender, address1, address2, city, state, postalcode)
VALUES (, , , , , , , , , , )
```
```
Figure 30 - 4 Incomplete SQL Code
```
f. Drag each Mapper variable from the Destination Mappings list into the generated INSERT
statement, in the correct position in the statement’s empty comma-separated VALUES list. This
should be done in the same order as the corresponding columns in the statement’s columns list. For
example, patientid is the first column listed in the INSERT statement, so drag the patientid Mapper
variable over into the first position in the VALUES list.


```
127 nextgen.com
```
```
The resulting statement should look like the following ( Note: The code here may look slightly
different due to text wrapping):
```
```
INSERT INTO patients (patientid, lastname, firstname, middlename,
dateofbirth, gender, address1, address2, city, state, postalcode)
VALUES (${row_patientid}, ${row_lastname}, ${row_firstname},
${row_middlename}, ${row_dateofbirth}, ${row_gender}, ${row_address1},
${row_address2}, ${ ow_city}, ${row_state}, ${row_postalcode})
```
```
Figure 30 - 5 Final INSERT Statement
```
7. Save and deploy the channel
8. Use the Dashboard’s Send Message tool to send a CSV batch to the channel
    a. In the Administrator’s Dashboard view, select the _Batch - Delimited Text to Database_ channel
    b. In the Dashboard Tasks menu, click Send Message. This opens the Message dialog (Figure 30 - 6 )

```
Figure 30 - 6 Send Message
```
```
c. In the dialog, click the Open Text File... button, browse to the folder
“C:\Training\Messages\Delimited”, and open the file “Patients.csv”
d. Click the Process Message button to send the message batch to the channel
```
**Results**
On the Dashboard, the statistics for the channel should now show 6 Received and 6 Sent. In the Channel
Messages view for the channel, you should see that a message has been generated for each record in the
delimited text batch file. Click on the Mappings tab in the Channel Messages view. As you select different
messages, you should see Source map variables for batchComplete, batchId, and batchSequenceId.
Assuming that you have only processed the batch once, all six messages should have the same batchId


```
128 nextgen.com
```
value. The batchSequenceId variable should contain a sequential value that increases from the first
message to the last. Finally, all messages except for the last should have a batchComplete value of false
(the last message should have a value of true).

Next, there should now be six new rows inserted into the Patients database table. You can view the
contents of the table using SQuirreL SQL Client. If you do not still have a connection to the mirthtraining
database in SQuirreL, see step 8 of Lab 11 (on page 49 ) to create the connection.

In SQuirreL, go to the SQL tab and execute the following query:

SELECT * FROM Patients

For each message that you sent to the channel, you should see a new row inserted into the Patients table
containing the data extracted from the message.


```
129 nextgen.com
```
## Lab 31 Create a CSV Batch File from HL7 Messages

**Objectives**
In this lab, you will create a channel that reads multiple HL7 message files and creates a single CSV
(comma-separated value) batch file from the patient demographic data in those messages. The resulting
batch file will have a header row with the column names, and one record row for each HL7 message that
was processed.

The channel will have File Reader as its source connector. The channel will then create the batch file from
all files read within a single poll of the File Reader. The channel then uses two File Writer destinations using
the append mode to create the batch file. The first destination writes the header row to the batch file and is
only executed when processing the first message in the poll. The second destination uses Message Builder
transformer steps to create a Delimited Text record from the patient data in the inbound HL7 message and
writes that record to the batch file.

The lab also contains a second optional, more advanced part. This part adds a third destination, a
JavaScript Writer, that uses JavaScript code to rename the batch file, indicating that it is complete. This
destination will only be executed once all messages in the poll have been processed.

**Estimated Time to Complete**
12 - 15 minutes, plus 10 additional minutes for optional second part

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer
- Notepad++

**Step-By-Step**

1. Create a new channel named _Create CSV Batch from HL7 Messages_
2. Configure the source connector as a File Reader that reads from a local folder
    a. On the Source tab, select File Reader in the Connector Type drop-down list
    b. Configure the File Reader properties as defined below in Table 31 - 1.

```
Setting Value
Directory /Training/inbox
Filename Filter Pattern *.hl7
After Processing Action Move
Move-to Directory /Training/processed/${channelName}
Note: You can drag-and-drop the ${channelName} variable from
the variable list to the right of this field
Move-to File Name ${COUNT}_${originalFilename}
Note: You can drag-and-drop the ${COUNT} and
${originalFilename} variables from the variable list to the right of
this field
Table 31 - 1 File Reader Settings
```
```
c. Leave all other File Reader properties as their defaults
```

```
130 nextgen.com
```
3. Configure the first destination connector as a File Writer that will write the batch header row to the file if
    processing the first message in the poll
    a. On the Destinations tab, rename the default File Writer destination to Write Header to Batch
       File
    b. Change the Connector Type to File Writer
    c. Configure the File Writer properties as defined below in Table 31 - 2

```
Setting Value
Directory /Training/outbox
File Name Batch_${pollId}.csv
Note: The ${pollId} variable is not available in the Destination
Mappings list, and must be manually typed
Template PatientID,LastName,FirstName,MiddleInit,DOB,Gender
Note: You can get this text from
“/Training/Messages/Delimited/Batch Header.csv”, or you can
type it in manually. Either way, make sure that you include a
single new line character after the end of the text (press Enter
with the cursor at the end of the text).
Table 31 - 2 File Writer Settings for Destination 1
```
```
d. Leave all other File Writer properties as their defaults
e. Add a filter rule to only execute the destination if processing the first message in the poll
i. Click Edit Filter in the Channel Tasks menu
ii. Click Add New Rule in the Filter Tasks menu
iii. In the Field property of the Rule Builder that was added, type $('pollSequenceId')
iv. For Condition, select Equals
v. Click the New button to add a new value to the Values list
vi. Edit the row, type 1 and press Enter to save the change
vii. The rule should now look like Figure 31 - 1 (below)
```
```
Figure 31 - 1 Rule Builder Filter for First Message in Poll
```
```
f. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel view
```

```
131 nextgen.com
```
4. Create a File Writer destination connector to append patient data from the HL7 message to the batch file
    a. Click New Destination in the Channel Tasks menu
    b. Rename the new destination as Write Record to Batch File
    c. Change the Connector Type to File Writer
    d. Configure the File Writer properties as defined below in Table 31 - 3

```
Setting Value
Directory /Training/outbox
File Name Batch_${pollId}.csv
Note: The ${pollId} variable is not available in the Destination
Mappings list, and must be manually typed
Template ${message.encodedData}
Note: You can drag-and-drop this value from the Encoded Data
entry in the Destination Mappings list
Table 31 - 3 File Writer Settings for Destination 2
```
5. Create the transformer steps to build a CSV record from the inbound HL7 message
    a. Click Edit Transformer in the Channel Tasks menu
    b. On the Message Templates tab, set the Inbound Message Template to any of the sample HL7
       messages in “/Training/Messages/HL7”
    c. For the Outbound Message Template, first select Delimited Text in the Data Type drop-down list
    d. Set the Outbound Message Template to the following:
    e. PatientID,LastName,FirstName,MiddleInit,DOB,Gender
    f. **Note:** You can get this text from “/Training/Messages/Delimited/Batch Header.csv”
    g. Click the Properties button next to the Data Type list for the Outbound Message Template
    h. For the Column Names property in the Template Serialization section, enter the same text that you
       provided for the Outbound Message Template (Figure 31 - 2 )

```
Figure 31 - 2 Outbound Properties for Delimited Text Outbound Message Template
```

```
132 nextgen.com
```
```
i. Click OK to close the Outbound Properties dialog
j. Create a Message Builder step for each column in the CSV outbound message template
i. Click the Message Trees tab
ii. For each entry in Table 31 - 4 below, find the HL7 component listed in the Inbound Message
Template, and drag the value from the Inbound Message Template Tree to the
corresponding node in the Outbound Message Template Tree. This will create a Message
Builder step that maps the field in the inbound message to the corresponding field in the
outbound message. Repeat until all components are mapped. If prompted to add the step
to an Iterator, click No.
Note: For more detailed instructions on creating Message Builder steps, please see Lab 6
on page 27
```
```
Inbound Message Template Field Outbound Message Template Field
PID.2.1 (PatientID – ID) row - PatientID
PID.5.1 (Patient Name – Family Name) row - LastName
PID.5.2 (Patient Name – Given Name) row - FirstName
PID.5.3 (Patient Name – Second and Further...) row - MiddleInit
PID.7.1 (Date/Time of Birth) row - DOB
PID.8.1 (Administrative Sex) row - Gender
Table 31 - 4 Mappings from Inbound Message Template to Outbound Message Template
```
```
k. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel view
```
6. Save and Deploy the channel
7. Copy and paste multiple sample HL7 message files (at least 3-4) all at once from the
    “/Training/Messages/HL7” folder to the “/Training/inbox” folder

**Results**
Within a few seconds of copying the HL7 messages files to the inbox folder, the channel will process them.
The Received count in the Dashboard statistics for the channel should be equal to the number of HL7
message files copied to the inbox. The Sent count for the channel should be equal to the Received count
plus one, due to the destination connector that only writes the header row for the first message.

Once the files have been processed, you should see that they have been moved from the “/Training/inbox”
folder to a new subfolder in the “/Training/processed” folder that matches the name of your channel.

In the “/Training/outbox” folder, you should see a new file with the name “Batch_ _PollID_ .csv”, where _PollID_ is
a 15-digit number representing the poll of the File Reader from which all the input files were read (for
example, “Batch_221588573663019.csv”.

The contents of the file should contain a single header row, followed by a row for each HL7 message
processed containing the basic patient demographic data from each message’s PID segment. An example
is shown below in Figure 31 - 3.


```
133 nextgen.com
```
```
PatientID,LastName,FirstName,MiddleInit,DOB,Gender
100146 ,O'Hallahan,Colleen,,19850704,F
880040,Conrad,Hermes,,19640202,M
1234567,Proctor,Morgan,A,19650601,F
1922001 ,Dixon,Clyde,S,19610615,M
```
**Figure 31 - 3 Example CSV Batch File Output**

In the Channel Messages view, select any of the channel messages for the “Write Record to Batch File”
destination (Figure 31 - 4 ).

**Figure 31 - 4 Poll Mapping Variables in Channel Messages View**

On the Mappings tab, you can see the polling-related Source Map variables that were used to build the
batch file. The pollId variable was used as part of the name of the generated file. The pollSequenceId was
used to determine if the header row needed to be written to the file (this variable will have a value of 1 for
the first message). The pollComplete variable indicates if the message is the last in the poll, thereby
indicating that the batch file can be considered complete.

**Part 2 (Optional)**
This part of the lab adds an extra destination onto the channel that renames the batch file once it is
complete (that is, once the data from the last message in the poll has been written to it). This requires
writing Java and JavaScript code in a JavaScript Writer.

**Step-By-Step 2**

8. Create a JavaScript Writer destination connector to rename the batch file to indicate it is completed
    a. Edit the same channel, and select the Destinations tab
    b. Click New Destination in the Channel Tasks menu
    c. Rename the new destination as Rename Completed Batch File
    d. Change the Connector Type to JavaScript Writer
    e. Add the following code to the JavaScript editor (comments optional):


```
134 nextgen.com
```
```
// Import the java.io package, which contains the File class
importPackage(java.io);
```
```
// Define a variable for the file name, matching the same format used in
// the previous two destinations
var fileName = "Batch_" + $('pollId') + ".csv";
```
```
// Create File objects for both the existing (source) file, and the new
// file name
var fileSource = new File("/Training/outbox/" + fileName);
var fileDest = new File("/Training/outbox/Completed_" + fileName);
```
```
// Rename the file
fileSource.renameTo(fileDest);
```
```
Figure 31 - 5 JavaScript Code to Rename Batch File
```
```
f. Add a filter rule to only execute the destination if processing the last message in the poll
i. Click Edit Filter in the Channel Tasks menu
ii. Click Add New Rule in the Filter Tasks menu
iii. In the Field property of the Rule Builder that was added, type $('pollComplete')
iv. For Condition, select Equals
v. Click the New button to add a new value to the Values list
vi. Edit the row, type true and press Enter to save the change
vii. The rule should now look like Figure 31 - 6 (below)
```
```
Figure 31 - 6 Rule Builder Filter for Poll Complete
```
```
g. Click Back to Channel in the Mirth Connect Views menu to return to the Edit Channel view
```
9. Save and Deploy the channel
10. Once again, copy and paste multiple sample HL7 message files (at least 3-4) all at once from the
    “/Training/Messages/HL7” folder to the “/Training/inbox” folder


```
135 nextgen.com
```
**Results 2**
The results will be similar to the first part, except now the Sent count will increase by two more than the
number of files processed. This is because, in addition to the destination that writes the header row, we now
also have the destination that renames the file executing once when the polling is complete.

In the “/Training/outbox” folder, you should now see a new CSV file containing the batch. However, now the
file name is prefixed with “Completed_”. For example, “Completed_Batch_221588573663019.csv”.


```
136 nextgen.com
```
## Lab 32 Create, Trigger an Alert

**Objectives**
In this lab, you will create an alert that will send an email to the address (or addresses) that you specify. To
trigger the alert, you will send a message to one of the channels that you created previously that sent to the
HL7 Inspector while the HL7 Inspector is not actively listening.

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- Any web browser, or whichever application you use to access your email

**Step-By-Step**

1. Configure SMTP Host settings used for sending alert emails
    a. Click Settings in the Mirth Connect menu to view the Settings view
    b. In the Email section on the Server tab of the Settings view, enter the SMTP Host settings from the
       Student Information sheet provided to you at the beginning of the course
    c. For the Default from Address, use any email address that you like, such as alerts@mirthtraining.com
    d. Click Save in the Server Tasks menu
2. Create an alert to send an email on an TCP Sender connection failure
    a. Click Alerts in the Mirth Connect menu
    b. Click New Alert in Alert Tasks menu to create a new alert
    c. In the Alert Name field, type TCP Sender Connection Alert
    d. Check the Enabled box to the right of the Alert Name field
    e. In the Errors list, check the box for Destination Connector
    f. In the Regex text box, type the following (be sure to use the exact case indicated):
       Connection refused
    g. In the Channels list, select the _JavaScript Transformers - Modify Message_ channel that you created
       in Lab 18 by clicking the name, and click the Enabled button above the list
       **Note:** Alternately, you could use any other channel that uses a TCP Sender, so long as the
       destination it’s sending to is not actively listening
    h. Click the Add button to the right of the Actions list
    i. In the new entry, leave the Protocol as Email, click the cell in the Recipient column to make it
       editable, and enter the email address at which you wish to receive the alert email. Press the Enter
       key to accept.
    j. Repeat steps hand i to add any additional email addresses at which you want to receive the alert
       email
    k. In the Subject field, type the following, including a space character at the end:
       A connection refused exception occurred in channel:
    l. At the end of the Email Subject field, drag the channelName variable from the Alert Variables list.
       The Email Subject field should now contain the following:
       A connection refused exception occurred in channel: ${channelName}


```
137 nextgen.com
```
```
m. In the Template field, type the following, including a space character at the end of each line:
Alert Name:
Channel:
Date:
Server ID:
Error:
n. For each of the variables in the Alert Variables list, drag over the variable and drop it after its
corresponding label. The Template field should now contain the following:
```
```
Alert Name: ${alertName}
Channel: ${channelName}
Date: ${date}
Server ID: ${serverId}
Error: ${error}
```
```
Figure 32 - 1 Final Contents for Alert's Template
```
3. Save the alert by clicking Save Alerts in the Alert Tasks menu
4. If your HL7 Inspector is still open and its Message Receiver is actively listening, shut down the Receiver
    by clicking the red stop button in the Message Receiver tab
5. Send a message to the _JavaScript Transformers_ channel using the Dashboard’s Send Message feature
    to trigger the alert

**Results**
Within a short while, you should receive an email (and/or SMS message) at the address (or addresses) that
you specified. The subject of the email should read “An error occurred in channel: JavaScript
Transformers”. The body of the email should look similar to the following:

```
Alert Name: TCP Sender Connection Alert
Channel: JavaScript Transformers
Date: Aug 29, 2013 8:12:42 PM
Server ID: 9816ff09-369a-42d5-8a65-7f5ff3c12600
Error: Destination Connector (TCP Sender) error ERROR MESSAGE: Error sending message via
TCP.
java.net.ConnectException: Connection refused: connect
at java.net.DualStackPlainSocketImpl.connect0(Native Method)
at java.net.DualStackPlainSocketImpl.socketConnect(Unknown Source)
at java.net.AbstractPlainSocketImpl.doConnect(Unknown Source)
at java.net.AbstractPlainSocketImpl.connectToAddress(Unknown Source)
at java.net.AbstractPlainSocketImpl.connect(Unknown Source)
at java.net.PlainSocketImpl.connect(Unknown Source)
at java.net.SocksSocketImpl.connect(Unknown Source)
at java.net.Socket.connect(Unknown Source)
at java.net.Socket.connect(Unknown Source)
at com.mirth.connect.connectors.tcp.SocketUtil.createSocket(SocketUtil.java:77)
at com.mirth.connect.connectors.tcp.SocketUtil.createSocket(SocketUtil.java:36)
at com.mirth.connect.connectors.tcp.SocketUtil.createSocket(SocketUtil.java:28)
```

```
138 nextgen.com
```
```
at com.mirth.connect.connectors.tcp.SocketUtil.createSocket(SocketUtil.java:24)
at com.mirth.connect.connectors.tcp.TcpDispatcher.send(TcpDispatcher.java:203)
at
com.mirth.connect.donkey.server.channel.DestinationConnector.handleSend(DestinationConnector.ja
va:527)
at
com.mirth.connect.donkey.server.channel.DestinationConnector.process(DestinationConnector.java:3
20)
at com.mirth.connect.donkey.server.channel.DestinationChain.call(DestinationChain.java:224)
at com.mirth.connect.donkey.server.channel.Channel.process(Channel.java:1347)
at com.mirth.connect.donkey.server.channel.Channel.dispatchRawMessage(Channel.java:912)
at
com.mirth.connect.donkey.server.channel.SourceConnector.dispatchRawMessage(SourceConnector.j
ava:157)
at com.mirth.connect.connectors.vm.VmReceiver.dispatchRawMessage(VmReceiver.java:59)
at
com.mirth.connect.server.controllers.DonkeyEngineController.dispatchRawMessage(DonkeyEngineC
ontroller.java:496)
at
com.mirth.connect.server.servlets.MessageObjectServlet$2.run(MessageObjectServlet.java:193)
at java.lang.Thread.run(Unknown Source)
```
```
at org.mule.impl.work.WorkerContext.run(WorkerContext.java:290)
at
edu.emory.mathcs.backport.java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.
java:1061)
at
edu.emory.mathcs.backport.java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecuto
r.java:575)
at java.lang.Thread.run(Thread.java:680)
```
**Figure 32 - 2 Contents of Alert Email Received**


```
139 nextgen.com
```
## Lab 33 Programmatically Trigger an Alert, Forward Alert Data to a Channel

**Objectives**
In this lab, you will see how you can programmatically trigger an alert from a JavaScript context, as well as
forward alert data to a channel for further processing. You will first create a channel that uses a JavaScript
filter to only accept ADT messages. If the message received is not an ADT, your JavaScript filter code will
call the alerts.sendAlert() method to trigger an alert. You will then create a second channel that receives
alert data, and simply writes that data to a log file. Finally, you will create an alert that will be triggered by
the first channel, and that uses the Channel action to forward the alert data to the second channel.

**Estimated Time to Complete**
15 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer
- Notepad++

**Step-By-Step**

1. Create the channel that will trigger a user-defined alert condition
    a. Create a new channel named _Alerts - Process Only ADTs_
    b. Create a filter on the source connector that will only accept ADT messages, and trigger an alert if the
       message is not an ADT
          i. Click Edit Filter in the Channel Tasks menu
ii. Click Add New Rule in the Filter Tasks menu
iii. For the new entry added to the filters list, double-click the cell in the Type column and select
JavaScript from the drop-down list (Figure 33 - 1 )

```
Figure 33 - 1 Selecting the JavaScript Filter Type
```
```
iv. In the JavaScript editor for the filter rule, type the code below in Figure 33 - 2
Note: For the first line of code, you can drag the E4X for getting the value from MSH.9.1
from the Message Trees tab if you have an Inbound Message Template set
```

```
140 nextgen.com
```
```
var messageType = msg['MSH']['MSH.9']['MSH.9.1'].toString();
```
```
if (messageType != "ADT")
{
alerts.sendAlert("Received invalid message type: " + messageType);
return false;
}
```
```
return true;
```
```
Figure 33 - 2 Code for JavaScript Filter to Trigger Alert for Non-ADT Messages
```
```
c. Leave the connector types for the source connector and default destination connector as Channel
Reader and Channel Writer, respectively
d. Save and deploy the channel
```
2. Create the channel that will receive the alert data and write it to a log file
    a. Create a new channel named _Alerts - Log Alert Data_
    b. Change the inbound and outbound data types to Raw for all connectors
       i. On the Summary tab of the Edit Channel view, click the Set Data Types button to open the
          Set Data Types dialog (Figure 21 - 2 )

```
Figure 33 - 3 Set Data Types Dialog with Data Types Set to Raw
```
```
ii. Select the Bulk Edit radio button at the top of the dialog
iii. Select the “All” checkbox that appears
iv. In the Inbound Properties section, select “Raw” from the data type drop-down list
v. In the Outbound Properties section, select “Raw” from the data type drop-down list
vi. Click the OK button to close the dialog
c. Leave the Connector Type for the source connector as a Channel Reader
```

```
141 nextgen.com
```
```
d. Configure the default destination connector as a File Writer that writes the received alert data to a
log file
i. Rename the destination to Write Alert to Log File (optional)
ii. Change the Connector Type to File Writer
iii. In the File Writer Settings section, specify the settings as shown below in Table 33 - 1 :
Setting Value
Directory /Training/outbox
File Name Alert History.log
Template ${message.encodedData}
Note: You can drag-and-drop this value from the Encoded Data entry in the
Destination Mappings list
Table 33 - 1 File Writer Settings
```
```
e. Save and deploy the channel
```
3. Create the alert that will be triggered when the channel created in Step 1 receives a non-ADT message
    a. Click Alerts in the Mirth Connect menu
    b. Click New Alert in Alert Tasks menu to create a new alert
    c. In the Alert Name field, type Invalid Message Type Alert
    d. Check the Enabled box to the right of the Alert Name field
    e. In the Errors list, check the box for “User Defined Transformer”
    f. In the Regex text box, type the following (be sure to use the exact case indicated, and do not include
       any extra spaces or carriage returns after the text):
       invalid message type
    g. In the Channels list, select the _Alerts - Process Only ADTs_ channel that you created in Step 1 by
       clicking the name, and click the Enabled button above the list

```
Figure 33 - 4 Channels List with Channel Enabled
```
```
h. Add a Channel action to forward the alert data to the Alerts - Log Alert Data channel
i. Click the Add button to the right of the Actions list
ii. In the new entry, select Channel from the drop-down list in the Protocol column, and select the
Alerts - Log Alert Data channel that you created in Step 1 from the drop-down list in the
Recipient column (Figure 33 - 5 )
```

```
142 nextgen.com
```
```
Figure 33 - 5 Selecting Channel as Alert Action
```
```
i. In the Template field, type the following, including a space character at the end of each line:
Date:
Alert Name:
Channel:
Server ID:
Error:
j. For each of the variables in the Alert Variables list, drag over the variable and drop it after its
corresponding label. The Template field should now contain the following:
```
```
Date: ${date}
Alert Name: ${alertName}
Channel: ${channelName}
Server ID: ${serverId}
Error: ${error}
```
```
Figure 33 - 6 Final Contents for Alert's Template
```
```
k. Save the alert by clicking Save Alert in the Alert Edit Tasks menu
l. If you had not previously configured the SMTP Host in the Settings view (as done in Step 1 of Lab
31 ), you will see the warning shown below in Figure 33 - 7. Click OK to dismiss this warning
Note: Because you will not send any email alerts in this lab, configuration of an SMTP server is not
required
```
```
Figure 33 - 7 No SMTP Server Configured Warning
```
4. Go to the Dashboard view by clicking Dashboard in the Mirth Connect menu
5. Using the Dashboard’s Send Message tool, send any non-ADT message to the _Alerts - Process Only_
    _ADTs_ channel


```
143 nextgen.com
```
**Results**

After a few seconds, you should see that the statistics for the _Alerts - Process Only ADTs_ channel show 1
Received and 1 Filtered. You should also see that the statistics for the _Alerts - Log Alert Data_ channel
show 1 Received and 1 Sent. On the Alert Dashboard, you should see that the Alerted column shows a
value of 1.

In the “/Training/outbox” folder, you should now see a file named “Alert History.log”. In it, you should see the
data specified in the template for the alert that you created, such as shown below in Figure 33 - 8.

```
Date: Mar 10, 2017 1:33:53 PM
Alert Name: Invalid Message Type Alert
Channel: Alerts - Process Only ADTs
Server ID: 68be9612-c398- 4828 - 8c75-ed5f6e5412d3
Error: User Defined Transformer error
ERROR MESSAGE: Received invalid message type: ORM
```
**Figure 33 - 8 Example Alert Output**


```
144 nextgen.com
```
## Lab 34 Configure Data Pruner, Channel for Message Pruning

**Objectives**
In this lab, you will first configure an existing channel with messages to enable its message pruning settings
to prune messages older than one day. Next, you will configure the Data Pruner to prune messages,
including archiving the data. Finally, you will run the Data Pruner manually, and verify that the message
data has been archived to a file and then deleted from the database.

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- Windows File Explorer

**Step-By-Step**

1. Enable message pruning for one of the channels created in a previous lab
    a. In Channels view in the Administrator, select the channel _Rule Builder Filters_ (created in Lab 4), and
       click Edit Channel in the Channel Tasks menu
       **Note:** Alternatively, you could do this for any other channel that has messages. The Rule Builder
       Filters channel should have five messages.
    b. On the channel’s Summary tab, in the Message Pruning section, click the “Prune metadata older
       than...” radio button
    c. In the days text box for the same setting, type 1
    d. Leave all of the other Message Pruning settings as their defaults. The Message Pruning settings
       should now appear as in Figure 34 - 1 , below

```
Figure 34 - 1 Channel Message Pruning Settings
```
```
e. Save the channel
f. Deploy the channel (optional)
Note: Redeploying the channel is not required for the changes to the pruning settings to take effect.
```
2. Verify the message data for the channel (optional)


```
145 nextgen.com
```
```
a. From either the Channels or Dashboard view, select the channel Rule Builder Filters and click View
Messages in the corresponding Tasks menu
b. You should see the message data for the five messages processed as part of that lab (Figure 34 - 2 )
```
```
Figure 34 - 2 Messages for Rule Builder Filters Channel
```
3. Configure the Data Pruner
    a. Click Settings in the Mirth Connect menu, then select the Data Pruner tab
    b. In the Schedule section, select “Yes” for Enable (Figure 34 - 3 )

```
Figure 34 - 3 Data Pruner Schedule Settings
```
```
c. In the Archive Settings section, click “Yes” for Enable Archiving
d. From the Compression drop-down list, select “zip”
e. For Root Path, type: /Training/MessageArchive
f. For File Pattern, provide the following text:
message_${message.messageId}.xml
Note: You can get the ${message.messageId} reference by dragging from Message ID in the
variable mapping box to the right
```
```
g. Click Save in the Data Pruner Tasks menu
```
4. Run the Data Pruner
    a. In the Data Pruner Tasks menu, click Prune Now
    b. In the Status section, you should now see Current State as “Pruning events” and Current Process
       showing that it has been initiated (Figure 34 - 4 )

```
Figure 34 - 4 Data Pruner with Status Pruning Events
```

```
146 nextgen.com
```
```
c. After a few seconds, click Refresh in the Data Pruner Tasks menu to refresh the status. The status
should now show as “Not running”, with Last Process showing today’s date (Figure 34 - 5 )
```
```
Figure 34 - 5 Data Pruner Status Showing Completed Process
```
**Results**
Go to the Channel Messages view once again for the channel _Rule Builder Filters_. Since the messages that
were processed for that channel were older than one day, you should now see that all of the message data
has been pruned.

Using Windows Explorer, browse to the “/Training/” folder. Within it, you should now see a new folder called
“MessageArchive”. Within that folder is a ZIP file named with the ID of the _Rule Builder Filters_ channel.
Within the ZIP file, you should see five individual XML message files, one for each of the five messages that
were pruned.

**Figure 34 - 6 Data Pruner Message Archive File**


```
147 nextgen.com
```
## Lab 35 Change the Backend Database to PostgreSQL

**Objectives**
In this lab, you will first create a server configuration backup of the information in the current Derby
database. You will then configure the Connect Server to use PostgreSQL as its backend database. Next,
you will restore the server configuration backup file on the new database schema. Finally, you will change
the server configuration back to use the original Derby database.

**Estimated Time to Complete**
10 minutes

**Tools Used**

- Mirth Connect Administrator
- Mirth Connect Server Manager

**Step-By-Step**

1. Create a backup of the current server configuration
    a. Click Settings in the Mirth Connect menu
    b. On the Server tab of the Settings view, click Backup Config in the Server Tasks menu
    c. In the Save dialog, navigate to the “/Training/Backup” directory, and save the file with its default
       backup name
    d. You will see a dialog appear indicating that the server configuration file was created. Click the OK
       button
2. Configure the Connect Server to use the PostgreSQL database
    a. Exit the Administrator if it is open
    b. Change the Connect Server configuration to use the PostgreSQL database
       i. Open the Server Manager (Figure 35 - 1 )

```
Figure 35 - 1 Server Manager - Database Settings
```
```
ii. Click the Database tab
iii. In the Type drop-down list, select postgres
iv. Verify that the URL is now the following value:
jdbc:postgresql://localhost:5432/mirthdb
```

```
148 nextgen.com
```
```
v. In the Username field, type mirthtraining
vi. In the Password field, type mirthtraining
vii. Click the Apply button to save your changes
viii. Click the Service tab
ix. Click the Restart button to restart the Connect Server
```
3. Restart and log into the Administrator
    a. In the Server Manager, click the Administrator button to open the Administrator
    b. Log into the Administrator. Note that since any user login or password changes that you made will
       not be reflected in the new database instance, you will need to use the default username and
       password, admin/admin.
    c. After logging in, the Welcome dialog will once again appear, requiring you to overwrite the default
       user. Enter your user information in this dialog and click OK.
    d. Once logged into the Administrator, notice that there are no channels, code templates, alerts, etc.
4. Restore the server configuration (created in Step 1 ) to the new database
    a. Click Settings in the Mirth Connect menu
    b. On the Server tab of the Settings view, click Restore Config in the Server Tasks menu
    c. Browse to and open the server configuration backup file created in Step 1
    d. You will see a message confirming that you want to import the configuration, with options to deploy
       all channels after import and/or overwrite the Configuration Map (Figure 35 - 2 ). Leave the options as
       the defaults and click Yes

```
Figure 35 - 2 Import Configuration Confirmation Dialog
```
```
e. When the import is complete, a dialog will appear informing you that the configuration was
successfully restored (Figure 35 - 3 ). Click OK
```
```
Figure 35 - 3 Configuration Successfully Restored Notification
```
5. Explore the various views. You should now see all of the channels, alerts, settings, etc. that you had
    created from the original Derby database. Notice, however, that no messages or users were imported.
6. Exit the Administrator
7. Change the Connect Server configuration back to using the Derby database
    a. Open the Server Manager


```
149 nextgen.com
```
```
b. Click the Database tab
c. In the Type drop-down list, select derby
d. Click the Apply button to save your changes
e. Click the Service tab
f. Click the Restart button to restart the Connect Server
```
8. Once the service has started, click the Administrator button to open the Administrator

**Results**
Once you have completed all of the above steps, you should be back to where you started. In other words,
you should have all of your channels, etc., _including_ messages.


```
150 nextgen.com
```
## Lab 36 Create a Script File and Run the Command Line Interface in Script Mode

**Objectives**
In this lab, you will create a batch file and edit the Shell.bat file to execute the Shell Client in script mode.

**Estimated Time to Complete**
5 - 10 minutes

**Tools Used**

- Any text editor, such as Notepad++
- Windows Command Prompt
- Windows File Explorer

**Step-By-Step**

1. In a text editor such as Notepad++, create a new file
2. In the file, type the following:

```
channel stop *
exportcfg "\Training\Backup\ServerConfig.xml"
dump stats "\Training\Backup\Stats.txt"
resetstats
channel start *
```
3. Save the file as Script.txt in the Mirth Connect installation directory (usually “/Program Files/Mirth
    Connect”)
4. Open a Windows Command Prompt window
5. Change (cd) to the installation directory
6. Execute the CLI by typing the following command:
    mccommand – s Script.txt

**Results**
In the Command Prompt window, you should see output from the execution of the batch similar to what is
shown below (channels will vary depending upon what you have deployed):


```
151 nextgen.com
```
```
Connected to Mirth Connect server @ https://127.0.0.1:8443 (3.0.0.xxxx)
Executing statement: channel stop *
Channel Alert Test Stopped
Channel Sample Channel for Message Pruner Stopped
Channel Custom Response Stopped
Channel File Test Stopped
Executing statement: exportcfg "\Training\Backup\ServerConfig.xml"
Exporting Configuration
Configuration Export Complete.
Executing statement: dump stats "\Training\Backup\Stats.txt"
Stats written to \Training\Backup\Stats.txt
Executing statement: resetstats
Executing statement: channel start *
Channel Alert Test Started
Channel Sample Channel for Message Pruner Started
Channel Custom Response Started
Channel File Test Started
Disconnected from server.
```
**Figure 36 - 1 CLI Output in Scripted Mode**

In the Administrator, you should see that all Dashboard statistics (Received, Sent, etc.) have been reset to

0. In the “/Training/Backup” folder, you should see two new files: ServerConfig.xml and Stats.txt.
ServerConfig.xml is a server configuration backup file, the same as was created in Lab 21. Stats.txt is a
comma-separated value (CSV) file that contains the statistics (Received, Sent, etc.) for all channels.


```
152 nextgen.com
```
## Lab 37 Launch the Mirth Connect Administrator Using Java Web Start

**Objectives**
In this lab, you will launch the Mirth Connect Administrator using Java Web Start from any web browser.
This is the required method if you do not have the Administrator Launch installed. Note, however, that this
method requires installation of a Java Runtime Environment (JRE) prior to Java 11.

If this is your first attempt to launch the application after installation, you will also need to customize the
default user information after logging in.

**Estimated Time to Complete**
3 - 4 minutes.

**Tools Used**

- Any web browser, such as Internet Explorer or Firefox
- Mirth Connect Administrator

**Step-By-Step**

1. Launch the Mirth Connect Administrator from a web browser using Java Web Start
    a. Open the web browser of your choice
    b. In the browser’s address field, type the following URL:
       [http://localhost:8080](http://localhost:8080)
    c. Press Enter key. This will display the Java Web Start page for the Administrator (Figure 37 - 1 ).


```
153 nextgen.com
```
```
Figure 37 - 1 Java Web Start Page
```
d. Click the green Launch Mirth Connect Administrator button
e. Depending upon which web browser you are using, you may see a dialog similar to Figure 37 - 2
(below) asking what you want to do with the Web Start file (webstart.jnlp). Choose to open with Java
Web Start Launcher and click the OK button.

```
Figure 37 - 2 Open Java Web Start Dialog
```
f. As the application is downloaded and started, you will likely see a security warning indicating that the
application’s digital signature has been verified and asking if you want to run the application (Figure
37 - 3 ). Click the Run button.


```
154 nextgen.com
```
```
Figure 37 - 3 Java Application Security Warning
```
2. Once the Login dialog appears (Figure 37 - 4 ), provide the default credentials for logging into the
    Administrator

```
Figure 37 - 4 Connect Login
```
```
a. For the Server field, leave the default address: https://localhost:8443
b. For the Username field, type admin
c. For the Password field, type admin
d. Click the Login button
```
3. In the Welcome to Mirth Connect dialog (Figure 37 - 5 ), customize the default user information by entering
    information in each of the required fields (marked with a red asterisk). Note that you can keep the
    default username and password as admin/admin by re-entering those values in the corresponding fields,
    or you can enter a different username and password to overwrite admin/admin.


```
155 nextgen.com
```
```
Figure 37 - 5 Welcome to Connect
```
```
a. In the Username field, type admin to keep the username as admin, or type a new username to
change it
b. In the Password field, type admin to keep the password as admin, or type a new password to
change it
c. In the Confirm Password field, re-type the same password that you entered in the Password field
d. Note your username and password for future reference (optional)
```
```
Username:
```
```
Password:
e. Uncheck the box for “Register user with NextGen Healthcare”. This makes it so that First Name,
Last Name, Email, Organization, and Industry are no longer required fields
f. Click the Finish button
```
4. Next, the Notifications dialog will display (Figure 37 - 6 ), showing any news or important information about
    Mirth Connect.


```
156 nextgen.com
```
```
Figure 37 - 6 Notifications
```
```
a. Remove the check for the Show new notifications on login check box
b. Click the Close button
```
**Results**
You should now be logged into the Administrator. If you view the Users list by clicking Users in the Mirth
Connect menu (top, left-hand side of the Administrator window), you should see a single user with the
information entered in the Welcome dialog.


```
157 nextgen.com
```
## Lab 38 Manually Parse an HL7 Message

**Objectives**
In this lab, you will manually parse an HL7 message. You are given an HL7 message and a list of fields to
find. For each field indicated, find the segment in the message, then count from the segment name the
fields, then field components indicated by the HL7 field notation. Don’t forget that for the MSH segment, the
first field is the field delimiter (|).

**Estimated Time to Complete**
2 - 3 minutes.

**Step-By-Step**
For the following HL7 message and requested fields, manually parse the message to find the values for the
fields.

**MSH** |^~\&|MIRTHCONNECT|SMMC|||200907131519||ORM^O01|12345678|P|2.4|||AL|NE<CR>
**PID** |1|4223161584^^^Mirth^PN|4223161584|4223161584|Fry^Philip^J^^^||19720515|M|||
123 Von Karman^Apt. 10B^Irvine^CA^92612||949 555-1234||||||815- 16 - 2342|<CR>
**PV1** |1|O|SMMC|OP|||ShephardJ^Shephard^Jack^G^^^MD|BurkeJ^Burke^Juliet^F^^^MD||CARE||||
PHYSICIAN||||CLINIC||BC|||||||||||||||||||SMMC||REG|||20090712||||||<CR>
**ORC** |XO|801887.001|||R|N||||||||||<CR>
**OBR** |1|801887.001||MRS^Shephard^Jane MRI W/&W/O CONTRAST^70553|
|200907131230||||||||||ShephardJ^Shephard^Jack^G^^^MD||MR^20061213-0007|
||||||||1^^^200907131230^^R||||||||<CR>
**OBX** |1|NM|84295^SODIUM^GH|1|145|mmol/L|||||F|||20090422152300|GH<CR>
**OBX** |2|NM|84132^POTASSIUM^GH|2|5.2|mmol/L|||||F|||20090422152300|GH<CR>

MSH.4 (Sending Facility)

MSH.9 (Message Type)

MSH.12 (HL7 Version)

PID.5 (Patient Name)

```
PID.11.3 (Patient Address City)
```
```
PV1.44 (Admit Date/Time)
```
```
ORC.2 (Order Number)
```
```
OBX.3.2 (Observation Text)
```

```
158 nextgen.com
```
**Results**
MSH.4 = SMMC, MSH.9 = ORM^O01, MSH.12 = 2.4, PID.5 = Fry^Philip^J^^^, PID.11.3 = Irvine, PV1.44 = 20090712, ORC.2 = 801887.001,
OBX.3.2 = SODIUM _and_ POTASSIUM


nextgen.com

Section Three

Using the Third-Party

Applications



```
161 nextgen.com
```
## Application A HL7 Inspector Using the Third-Party Applications

**About**
HL7 Inspector is a third-party open-source application developed by elomagic. It can be used to both send
and receive HL7 version 2.x messages over a TCP/IP-based connection, such as MLLP. It displays
imported messages in a tree structure, allowing you to view the various levels of an HL7 message (segment,
field, component). HL7 Inspector also provides some very basic message editing capabilities.

For more information about using HL7 Inspector, visit [http://www.elomagic.de.](http://www.elomagic.de.)

**Sending Messages**
HL7 Inspector has both a message sender, as well as a message receiver. Each is opened in its own tab
within the HL7 Inspector window, and you can have both the sender and receiver open at the same time.
This section provides instructions for configuring the Message Sender and then sending a message. The
Message Sender can be used to send messages to a channel with a TCP Listener in MLLP transmission
mode.

**Configuring the Message Sender**

1. Open HL7 Inspector (if not already open) by clicking the HL7 Inspector icon in the Taskbar (or select All
    Programs > HL7 Inspector > HL7 Inspector from the Windows Start menu)

```
Figure A- 1 HL7 Inspector in the Windows Taskbar
```
2. Open HL7 Inspector’s Message Sender pane by clicking the Send Selected Messages toolbar button.
    This is the button with the red, upward-pointing arrow (Figure A- 2 )

```
Figure A- 2 Button to Open HL7 Inspector's Message Sender
```
3. In the Message Sender tab, click the button with the screwdriver and wench in the toolbar for the
    Message Sender pane to open the Send Options dialog (Figure A- 3 )


```
162 nextgen.com
```
```
Figure A- 3 HL7 Inspector Setup Sender Options Button
```
4. In the Send Options dialog, replace the default port value of the 2100 with the port number to which to
    send (Figure A- 4 ). This value should be the same as the Local Port value in the TCP Listener connector
    in your channel. If your channel is on an instance of Connect that is not running on your local host, also
    replace the default host value of localhost with the actual address of the host to which to send. The
    Send Options dialog also provides the ability to select the desired character set and MLLP frame
    encoding characters. However, in most situations, you will not need to change these values.

```
Figure A- 4 HL7 Inspector Send Options
```
5. Click OK to save your changes

HL7 Inspector is now configured to send messages. You will now need to import the message or messages
that you wish to send.

**Importing a Message**
To be able to send a message using HL7 Inspector, you must first import it into HL7 Inspector from a file.

1. Select File Open... from the File menu. Alternatively, you can click the File Open button from the HL7
    Inspector’s toolbar (Figure A- 5 ), or press Ctrl+O. This will open a standard file browser window.


```
163 nextgen.com
```
```
Figure A- 5 Button to Open/Import an HL7 Message from a File
```
2. In the file browser, navigate to the location of the file that you want to open, select the file, and click the
    Open button
3. Before actually importing the message, the Import Options dialog appears (Figure A- 6 ). You should not
    need to change any of the settings that you see in this dialog. Click the OK button to complete the
    import of the message.

```
Figure A- 6 Import Options Dialog
```
The HL7 message should now appear in the message tree area of the HL7 Inspector window. By default,
for each message that you import, you will only see the first line of the message (typically, the MSH
segment). However, you can view the entire contents of the message by clicking the “+” to the left of the line
to expand the message to view all segments. You can also expand segments to view each field, as well as
expand composite fields to view each individual field component.


```
164 nextgen.com
```
```
Figure A- 7 Imported HL7 Message in Message Tree, Expanded
```
**Importing Multiple Messages**
HL7 Inspector does not allow multiple messages to be imported at once using the above method. However,
this can be accomplished by dragging the files to import from Windows Explorer directly into HL7 Inspector.

1. In Windows Explorer select all of the files that you wish to import. To select a range of files in Windows
    Explorer, select the first file in the range, hold down the Shift key, and then select the last file in the
    range. To select multiple files individually, hold down the Ctrl key as you select each file.
2. Once you’ve selected all of the files you wish to import, drag the files into the message tree area (the
    grey area above the Message Sender tab) of the HL7 Inspector, holding down the mouse button as you
    drag, then releasing it once your mouse is above HL7’s Inspector’s message tree.
3. For each message that you are importing, the Import Options dialog (Figure A- 6 ) will appear. Click the
    OK button each time. For example, if you are importing 10 messages at once, the Import Options dialog
    will appear 10 times, and each time you will need to click the OK button.

**Sending the Message**

1. Select the message that you wish to send by clicking the top-level line (as shown in Figure A- 7 , above).
2. In the Message Sender tab’s toolbar, click the Send button (the blue “play” triangle) (Figure A- 8 ) to send
    the message.


```
165 nextgen.com
```
```
Figure A- 8 Send Button in Message Sender
```
Upon sending the message, HL7 Inspector will display connection and message information in the Message
Sender window (Figure A- 9 ). Included in this output:

1. Connection to the destination address and port
2. Message sent, including all frame encoding characters (highlighted in magenta)
3. Acknowledgement message received from destination system, including all frame encoding characters
4. Evaluation on acknowledgement code in ACK
5. Disconnection from the destination system

```
Figure A- 9 Message Sender Output
```
You can also send multiple messages at once, simply by selecting each message that you wish to send
(holding down the Ctrl key as you select each message), then clicking the Send button. This will send each
message selected in the order in which they appear in the message tree.


```
166 nextgen.com
```
**Receiving Messages**
In addition to sending messages, HL7 Inspector can also receive messages sent over an MLLP connection.
This feature can be used to test a channel with a TCP Sender destination connector in MLLP transmission
mode. HL7 Inspector’s Message Receiver will automatically create an ACK message to send back on the
same connection on which the original message was sent.

**Configuring the Message Receiver**

1. Open HL7 Inspector if not already open
2. From the Tools menu, select Receive Messages to open the Message Receiver tab (or click the button
    on the toolbar with the downward-pointing green arrow) (Figure A- 10 ). This opens the Message
    Receiver tab at the bottom of the window.

```
Figure A- 10 Button to Open HL7 Inspector's Message Receiver
```
```
a. In the Message Receiver tab, click the “Setup network” button (second button from the right) (Figure
A- 11 )
```
```
Figure A- 11 HL7 Inspector Setup Network Button
```
```
b. In the Receive Network Setup dialog that appears, type the port specified as the Remote Port in your
channel’s TCP Sender (e.g., 6660), and check the Reuse box (Figure A- 12 ).
IMPORTANT! Do not forget to check the Reuse checkbox. The Message Receiver will not be able
to receive messages unless it is checked.
```
```
Figure A- 12 HL7 Inspector Receive Network Setup Dialog
```

```
167 nextgen.com
```
```
c. Click OK to accept the changes
d. Click the “Start receiving message service” button (the blue “play” triangle) to start the receiver
listening on the specified port (Figure A- 13 ). The Message Receiver window should now display the
message (with the port specified in the Receive Network Setup dialog):
Listening on port 6660
```
```
Note: Upon starting the Message Receiver, you may see a Windows dialog asking to allow access
to port 6660. If so, click the “Allow” button.
```
```
Figure A- 13 HL7 Inspector Start Receiving Message Service Button
```
HL7 Inspector is now configured to receive messages.

**Receiving a Message**
For each message received by HL7 Inspector, it will display information about the transaction in the
Message Receiver window (Figure A- 14 ). This information includes:

1. Address of the message sender
2. Message received, including all frame encoding characters (highlighted in magenta)
3. Sending of acknowledgement
4. End of stream detection

Each message received will also appear in the message tree, along with any other messages received or
imported.


```
168 nextgen.com
```
**Figure A- 14 Message Receiver Output**
