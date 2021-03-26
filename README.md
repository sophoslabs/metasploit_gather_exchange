Metasploit Post-Exploitation Gather module for Exchange Server
--------------------------------------------------------------

A Metasploit framework module for gathering information from an Exchange Server.

The module gathers information from an Exchange Server, running on a compromised target, over a Meterpreter session.

It uses the "Exchange Management Shell," a collection of PowerShell scripts installed along with Exchange Server.

See article on the Sophos website for more details: https://news.sophos.com/en-us/2021/03/09/sophoslabs-offensive-security-releases-post-exploitation-tool-for-exchange/

**The module has been merged into Metasploit Framework, you can now use it directly from an up-to-date Metasploit installation.**

## Usage
![usage](usage1.png)

Two actions are supported:

#### `LIST` (default action)
Query the local Exchange server and retrieve basic information about each of the mailboxes it hosts.

![list](usage2.png)

#### `EXPORT`
Export and download a chosen mailbox in the form of a .PST file, with support for an optional filter keyword.

Options:
* `MAILBOX`: Required, Display name or e-mail address of mailbox to export
* `FILTER`: Optional, can be used to refine the exported results (e.g. only export items received on a particular date)
   
    For a list of valid filters, see https://docs.microsoft.com/en-us/exchange/filterable-properties-for-the-contentfilter-parameter

![export](usage3.png)

-----------------

The executing user has to be assigned to the "Organization Management" role group for the module to successfully run.

The module might not function correctly if Windows Defender is enabled and detects the PowerShell script as malicious.

Tested on on-premises installations of Exchange Server 2010 on Windows Server 2012 R2 and Exchange Server 2016 on Windows Server 2016. It has not been tested in cloud-hosted installations of Exchange.
