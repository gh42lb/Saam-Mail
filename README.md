## Overview

Saam-Mail v1.0.3 Beta release de WH6GGO.

Saam-Mail allows the transfer of error-corrected emails/forms/messages to groups of stations in real time over ham radio. Saam-Mail uses the SAAMFRAM protocol. 

Saam-Mail is written in python and will run on many python supported platforms.

Saam-Mail is confirmed to work well on both the raspberry pi and the Windows Beelink mini computing platform. These platforms use very little power and are, in this regard, ideal for off-grid and/or mobile setups.


#### Features
* Critical Messages: Enables transfer of fully verified, error-corrected emails/forms/messages to ham radio stations in real time.
* Group Communication: Capable of real time Peer to Peer, Peer to Group, Group to Peer** and Group to Group** mode communications.
* Resilience: Optimized data transfer protocol for increased performance and resilience to adverse band conditions.
* Integration: Integrates with JS8Call, Fldigi, Winlink and Pat Winlink applications.
* Cross-Platform: Runs on Windows, Linux and any other platform supporting python + related libraries.
* Flexibility: Multiple message delivery techniques including push, pull, store and forward, relay, active session, passive mode.
* Mesh Node: Ad-hoc mesh node functionality provided out-of-the-box, including: relay, hub, gateway, RX or TX end node,
* Notifications: Stub messages provide notification to the group of any pending messages waiting to be sent.
* Data Compression: Uses a variety of data compression techniques inluding dictionary compression and run length encoding.
* Customized Interface: Email style interface with inbox, outbox, relay box and sent box, utilizing notebook style and customized GUI controls.
* 32 Modulation Modes: Supports a wide variety of underlying modulations (28 fldigi modes and 4 js8 modes) including JS8, PSK, QPSK, BPSK, DominoEX, 8PSK and Olivia.
* Extendable: Form designer built-in with many pre-built ICS form templates and standard templates included.
* Please note:- Group to Peer and Group to Group is currently available only with JS8Call

## Quick Start Guide

### Configuration
Saam-Mail supports JS8Call application and fldigi application. Choose the platform you are going to use then follow the instructions below as appropriate.

#### JS8Call Configuration

JS8Call is configured as follows:

Mode Menu/Enable Auto Reply - checked
This setting is required for the text transfers between js8call and saam-mail to function correctly

File/Settings/Reporting tab, under the API section:
TCP Server Hostname: 127.0.0.1   Enable TCP Server API - checked
TCP Server Port:     2442        Accept TCP Requests   - checked
TCP Max Connections: 1 (if using saam-mail only) or 2 (if using saam-mail + js8-net concurrently)

When you are ready to transmit, adjust the mode speed in JS8 as required (slow, normal, fast, turbo) and make sure
 the TX button at the top right is enabled.


#### FLDIGI Configuration:

The default settings in fldigi work well. 
If you are having issues connecting, check the xmlrpc settings in fldigi. Make sure Fldigi xmlrpc external api is enabled and the ip and port are set to 127.0.0.1 and 7362 respectively.


#### Python Configuration

Make sure python 3 is installed along with the following modules: PySimpleGUI, sys, threading, json, random, getopt, datetime, socket, time, select, calendar, gps, crc
This can be done using the pip3 command for any missing modules e.g. pip3 install pysimplegui
Please note saam_mail is available for python 3 only.

### Download the Application

#### Windows
Download the saam_mail.exe file to your chosen directory along with the ICS_Form_Templates.tpl and Standard_Templates.tpl file

#### Raspberry pi
Download the saam-mail file to your chosen directory along with the ICS_Form_Templates.tpl and Standard_Templates.tpl file
make sure the binary is executeable: sudo chmod +x ./saam_mail

#### Python
Download the saam-mail python files into your chosen directory along with the ICS_Form_Templates.tpl and Standard_Templates.tpl file



### Running the Application

running with fldigi using windows binary : .\samm_mail.exe --opmode=fldigi
running with js8call using windows binary: .\samm_mail.exe --opmode=js8call

running with fldigi using raspberry pi binary : ./samm_mail --opmode=fldigi
running with js8call using raspberry pi binary: ./samm_mail --opmode=js8call

running with fldigi : python3 ./samm_mail.py --opmode=fldigi
running with js8call: python3 ./samm_mail.py --opmode=js8call

If you wish to use a different fldigi xmlrpc port or ip this can be specified using the fldigi=<IP>:<port> command line option:

e.g.
.\saam-mail.exe --opmode=fldigi fldigi=127.0.0.1:7362

similarly, if you wish to use a different js8call JSON port or ip this can be specified using the js8call=<IP>:<port> command line option:

e.g.
.\saam-mail.exe --opmode=js8call js8call=127.0.0.1:2442


if everything is installed correctly, samm_mail will connect to fldigi or js8call and display the main window.

Now go to the settings tab and fill out your information.
At a minimum, this must include your call sign and chosen group name.
Also make sure one of the template files is loaded into the application on the settings tab


### Sending your first saam_mail form

Enter the callsign for the station you wish to connect to in the 'Connect To:' field which is flashing red and green on the main page area.

The receiving station should enter your callsign into the same field on their application.

Make sure that both the sending station and the receiving station have specified the same group name in the myinfo tab

Click the compose tab, select the form to use then click the compose message button. 

In the to field enter one or more call signs of the receiving station delimited with semicolons. 

Compose a message then click post to outbox

Click the outbox tab then select the message and click send.



enjoy :)

73 de WH6GGO


## Copyright/License

MIT License

Copyright (c) 2022 Lawrence Byng

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


