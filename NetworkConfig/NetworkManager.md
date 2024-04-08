## Network Manager
    Of course if you wanted to have your system's networking up and running automatically there is something already in place for that. 
    Most distributions utilize the NetworkManager daemon to configure their networks automatically.

    You'll notice NetworkManager in the form of an applet somewhere on your desktop taskbar if you are using a GUI. 
    As you can see it manages your network's hardware and connection information. 
    For instance on startup, NetworkManager will gather network hardware information, 
    search for connections to wireless, wired, etc. and then activates it.

    There are also command-line tools to interact with NetworkManager:

    nm-tool

    nm-tools reports NetworkManager's state and it's devices
## nmcli
    The nmcli command allows you to control and modify NetworkManager, see the manpage for more details.
