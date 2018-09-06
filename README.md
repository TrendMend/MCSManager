Simple, easy to use, multi-instance, lightweight Minecraft Server control panel

[Chinese Simplified] (Readme.md) | [Chinese Traditional] (README-traditional.md)

<br />

welcome
-----------
![Software screenshot](http://39.108.57.206/public/MCSM_A.png)
**Note: ** Due to occasional replacement reasons, the current screenshots are not necessarily up to date.

<br />

Rapid expansion
-----------
We use the easiest way to build the entire application, and most developers can easily modify it and develop it according to the protocol. You will find that this may be a `Minecraft` server management tool that works well for you, supporting most of the mainstream servers.

And, we will try to reduce the expansion of learning costs as much as possible to help you better extend and customize, let a fully owned `Minecraft` server manager appear.

<br />

Operating environment
-----------
- Our deployment is extremely simple. Under the `Master` branch, our design is to download and run, no need to compile with any configuration, except to install an environment.

- `Node.js` >= 8.0
- `Download Mirror Site`: [https://npm.taobao.org/mirrors/node/v8.0.0/] (https://npm.taobao.org/mirrors/node/v8.0.0/)

<br />

Demo environment
-----------
- Address: [https://link.suwings.top/](https://link.suwings.top/)
- Account number: `public` Password: `123456`
- Account number: `public2` Password: `1234567`
- Account number: `#master` Password: `<不不开>`

> Just open the general account to give the demo, the management account is not open, want to know more, please download the experience.

<br />

Running on Windows
-----------

**Method 1 (Simplified Chinese only)**

Download and properly install the `Node` environment:

Download the source code and extract it: [https://github.com/Suwings/MCSManager/archive/master.zip](https://github.com/Suwings/MCSManager/archive/master.zip)

Enter the program source code directory and open the command console in the current directory

Execute the command `npm install --production`

Execute the command `node app.js` or `npm start`


**Method 2 (including Simplified/Traditional version)**

For some reason, you may not want to install these operating environments, so we have given a green packaged runtime environment, and the download can be used directly.

Download directly to run:

https://pan.baidu.com/s/1bpbB8Az (Chinese Simplified/Traditional Chinese Version Download Address)


**Note: ** The download provided by Baidu's network disk is packaged and integrated. We will not pack the small version update, which means that the latest version cannot be followed in real time.

<br />


Running on Linux
-----------
- Relatively speaking, this may be easier. Assuring that your version of the node is correct and the git tool is working, it's easy to install and run.

```bash
Git clone https://github.com/Suwings/MCSManager.git
Cd MCSManager
Npm install --production
Node app.js # or npm start
```

> If you still can't run, please click [here] (https://github.com/Suwings/MCSManager/wiki/Linux-%E4%B8%8B%E5%AE%89%E8%A3%85%E4 %B8%8E%E4%BD%BF%E7%94%A8%E8%AF%A6%E8%A7%A3)

<br />

Wiki
---------
We have some common problems and details, and we have integrated them into `Wiki`.

You are welcome to read [Wiki] (https://github.com/Suwings/MCSManager/wiki) and make suggestions.

<br />

Project directory structure
-----------
**Note: ** Not all files in the directory We recommend that you make changes!

| Directory Name | Details / Explanation |
| ------------------------ | ------------------------ -------------------------------------------------- ------------------- |
| **property.js** | Control Panel Profile |
| **core/logo.txt** | console output logo text|
| **public/** |All front-end code, resource directories, front and back separation, using ws and ajax communication|
| **public/login/** | Pure UI Logical Login Page |
| **public/template/** | Front-end business templates, each with a lifecycle, start and end. |
| **public/onlinefs_public/** | File Online Management Module Front End All Code |
| **public/common/js/meum.js** | Control Panel Left Menu List |
| **public/common/js/login.js** | Universal Login Process Logic, Reusable in Various HTML Login Templates |
| **server/server_core** |Minecraft server core directory, including server files, configuration, mod, and plugins |
| **server/x.json** |Minecraft Server Panel Profile |
| **users/x.json** | Control Panel User Profile |
| **route/** | Controller, HTTP request business logic layer (secondary extension) |
**route/websocket/** | Controller, Webscoket request business logic layer (can be expanded twice)|
| **core/Process/** |Minecraft Server Class Implementation |
| **core/User/** |User Class Implementation|
| **core/DataModel.js** | Data persistence model, almost all configured I/O models |
**model/** |Model layer for providing controllers and servers, user operations, and design pattern models |
| **helper/** | Business Logic Auxiliary Layer for Aiding and Reusing Business Logic |
**ftpd/** |FTP standalone module, where ftpserver.js has implemented abstraction ftpServerInterface interface|
| **onlinefs/** | File Management Standalone Module ([Suwings/IndependentFileManager](https://github.com/Suwings/IndependentFileManager))|

<br />

Browser compatibility
-----------
- `ECMAScript 5` standard
- `IE 10+` `Chrome` `Firefox` `Safari` `Opera` and other modern mainstream browsers

**Exception: ** File online management interface requires `IE 11+`

<br />


Configuration file
-----------
Our configuration file is the `property.js` file in the program directory, which is automatically generated the first time you run it.

> Attention! The old version of the McserverConfig.json file is completely deprecated.

> All configurations will now be summarized in this file.

> This file does not conflict with the github version and will not be automatically overwritten when updated

<br />


Custom design
-----------
If you are using it internally or for learning, you can make any changes to the front end and back end, including copyright notices.

> Attention! When you update the version, you may overwrite your custom modifications.

> Of course, not all files need to be overwritten, and it is not necessary to use the new version.

<br />

FTP service
-----------
The FTP module uses the passive transfer mode, and the transfer command uses the `10022` (changeable) port by default;

Transferring data requires a port segment, the default is `20010` - `20100`;

To ensure proper use of the FTP service, configure your firewall settings to open these port ranges.

> Of course, we offer online file management, so you don't have to use FTP completely.

<br />

Reverse proxy and SSL
-----------

Although there is no Https by default, you may not be comfortable with the public network, but we do not pass the plaintext password to ensure that the password of your account is difficult to disclose.

The specific password passing process can refer to [Click here to jump] (https://github.com/Suwings/MCSManager/wiki/%E7%99%BB%E5%BD%95%E5%AF%86%E7%A0 %81%E4%BC%A0%E9%80%92%E8%BF%87%E7%A8%8B%E5%9B%BE)

**Property file**

Before the reverse proxy, you can, but do not have to read the `property.js` file

> There are various settings, including gzip compression, port and ip binding, and more.

**Implement HTTPS and WSS**

Open the front-end URL location file `public/common/URL.js` and change http and ws to https and wss;

Guarantee that all requests from the front end are https and wss
> This file will not conflict with the github version and will not be overwritten when updating. Please feel free to modify it.

**Reverse agent**

Please use the reverse proxy to complete the backend, or modify the Express initialization app yourself.

**Note:** [Nginx Reverse Proxy Note] (https://github.com/Suwings/MCSManager/issues/22) | [Apache Reverse Proxy Note] (https://github.com/Suwings/MCSManager /issues/34)

<br />

Virtualization
-----------
**Note** This is a lightweight management panel. There is no integrated virtualization container. Please pay attention to the risk of providing a stranger server.

But you can implement a holistic virtualization container to keep your host safe.

In addition, there is also a custom boot command (can be disabled) function when the server starts. This allows you to start the server not only by running java related commands, but also by running command scripts. You can try more skill combinations. To achieve your needs, for example, start a server and start a script to do something.

**Overall virtualization**

Although we didn't create a virtualization container for each instance server, you could have an overall virtualized container for the entire control panel.

> For more information, please refer to [Wiki](https://github.com/Suwings/MCSManager/wiki/Linux-Docker-%E6%95%B4%E4%BD%93%E5%8C%96%E8%A7 %A3%E5%86%B3%E6%96%B9%E6%A1%88)


<br />


Privilege system
-----------
In particular, in order to simplify the panel permissions system

`Administrator account` Any user who starts with the # character is a management account, such as `#master` `#admin` `#test`

`Normal account` Users who do not start with the # character, such as `test` `usernameww` `xxx`

A server that can be managed by a normal account can only be set by an administrative account. The management account can manage any server and can manage all users.

For specific use, I think you only need to run to know that the design is very simple.

<br />

Problem report
-----------
Welcome everyone to find any BUG timely feedback to me, it must be repaired in time

<br />

Agreement and copyright
-----------
The program is based on [GNU Affero General Public License v3.0] (./LICENSE "GNU Affero General Public License v3.0") open source free software.

You can modify and redistribute this program in accordance with the AGPLv3 protocol.

Or, when learning or private (internal) use, under the principle of non-public release, you can ignore this ** agreement and copyright **, because this does not bind you, and we welcome this.

<br />