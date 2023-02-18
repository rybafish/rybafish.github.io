# Connection Manager

<span style="color:blue">Draft version</span>

Rybafish has a little connection manager allowing you to configure and save several connections to several data sources.

To init the connection manager you just go File -> Connect or Alt+C

![image](https://user-images.githubusercontent.com/53466066/219866894-982b5426-0770-44ba-ae09-6e68be4148fb.png)

Note: connection type selection is only available for versions above 093beta0 and experimental: True in config.yaml, see below.

Connections are saved in file connections.yaml. The default loaction is current RybaFIsh instance folder, but in can be configured by setting [connectionsFile](/config#connectionsFile).

Passwords are stored in encripted form in the same file.

### Connection type

Connection type is only available when [experimental](/config) features are enabled.

Currently two connection types are suppoeted: HANA DB and SQLLite.

<span style="color:blue">TBD</span>


