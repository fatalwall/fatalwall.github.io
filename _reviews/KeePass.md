---
layout: review
title: KeePass 2.0 - Password Vault
url: https://keepass.info/
Cost: Free (GPL v2)
rating: 4
tags: software windows security password vault 
---
Password for this password for that. I have so many that it is litterally impossible to keep track of. Do you write them down? Store them in an excel document? Use the same credientials accross multiple websites? What happens when one website is compromised? To protect against all of this many are turning to password vaults to allow a unique username and password per website. Now comes the question of which vault to use and why. My colleges and I often time debate on what tool is best. Do you choose a cloud hosted solutions because it provies ease of use and doesnt lock you to any specific device? This tends to lead you to more issues of uncertanties. Do you have any way of validating that they do what they claim? What level of access do employees have? I have found KeePass 2.0 to be the best option to date for balancing my security concerns and desire to avoid complicating or slowing down my work stream.

<!--more-->
**Pros**: 
 - All software is installed locally.
 - Master Password to encrypt the password vault
 - Key File to encrypt the password vault which can be stored seprately from your vault
 - Control where your Vault is stored
   - locally computer
   - USB drive
   - DropBox
   - OneDrive
   - Synology Drive
 - Open source allowing someone like myself the ability to audit the code
 - Version control of Entry records
 - Plugin support
 - URL Override's for quick double click launch and login

**Cons**: 
 - Initial setup is often complicated even for a mid level IT profesional
 - User interface is lackluster and could do with a an update
 
## Tips and Tricks
### Remote Desctop Connection (RDP)
Quickly launching MSTSC on Windows to remotely control Servers and Desktops. If dealing with multiple systems using the same credentials it is recomended that you make a seprate entity with the username and password and link the individual server entity to it. This will limit maintenance complexities when password resets occur.

**Support**
 - Most special characters in password
 - Alternative Port
 - Temporary use of Microsoft Credential Store to pass credentials
 - Quick removal of credentials from store to limit risk (~5 seconds)
 - If you are using local server credentials replace domain with a period (.\username)
 
```batch
cmd://
  cmd /c "cmdkey /generic:TERMSRV/{URL:HOST} /user:"{USERNAME}" /pass:"{PASSWORD}" 
    && start /b mstsc /v:{URL:RMVSCM} 
    && timeout /t 5 /nobreak 
    && cmdkey /delete:TERMSRV/{URL:HOST}"
```
*Note: Use the code snippet from below when entering into KeePass. Extra spaces can throw off the ability for commands to process via KeePass.*
#### Required Entry Values
 - User Name: Domain\Username
 - Passwor: **********
 - URL: rdp://ServerName or rdp://ServerName:port

#### URL Override
Schema: rdp
```batch
cmd://cmd /c "cmdkey /generic:TERMSRV/{URL:HOST} /user:"{USERNAME}" /pass:"{PASSWORD}" && start /b mstsc /v:{URL:RMVSCM} && timeout /t 5 /nobreak && cmdkey /delete:TERMSRV/{URL:HOST}"
```
### Example for Testing Variables
When building your own custom URL Overrides it is helpful to use something like the below to validate your pulling the correct details

Useing /k keeps the command window open
Useing /c minimizes the visibility of the command window

```batch
cmd:// 
  cmd /k 
    "echo Testing Output of KeePass Variables 
    & echo. URL Without Schema: "{URL:RMVSCM}" 
    & echo. HostName Only: "{URL:HOST}" 
    & echo. User: "{USERNAME}" 
    & echo. Pass: "{PASSWORD}" 
    & echo. Done"
```
*Note: Use the code snippet from below when entering into KeePass. Extra spaces can throw off the ability for commands to process via KeePass.*
#### Required Entry Values
 - User Name: Domain\Username
 - Passwor: **********
 - URL: test://ServerName:port

#### URL Override
Schema: test
```batch
cmd://cmd /k "echo Testing Output of KeePass Variables & echo. URL Without Schema: "{URL:RMVSCM}" & echo. HostName Only: "{URL:HOST}" & echo. User: "{USERNAME}" & echo. Pass: "{PASSWORD}" & echo. Done"
```
