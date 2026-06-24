# Remote Grading And Remote Monitor

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Remote Grading and Remote Monitor

The pages ahead walk through configuring Remote Grading with a pair of distinct DaVinci Resolve systems sitting in separate locations and linked over the internet, so that one of them can drive the other remotely for color grading. DaVinci Remote Monitor, by contrast, lets you push a high quality video signal out of one DaVinci Resolve system toward another workstation, whether across the internet or over the same network.

### Introduction to Remote Grading

So that colorists can collaborate live with clients anywhere on the planet, DaVinci Resolve provides a remote grading capability. Two identical DaVinci Resolve systems can be kept in sync over an Internet connection, so any change the colorist makes on their workstation appears at once on the remote client’s workstation. Cue commands stay synchronized too, keeping both systems parked on the very same frame in the Timeline. Begin or halt playback on the colorist’s DaVinci Resolve and the remote client system begins or halts right along with it. For the length of a remote grading session, whatever the user types or clicks at the remote client’s DaVinci Resolve workstation is disregarded. At present the remote grading feature handles color correction alone, with no editing or conforming permitted mid-session. Both the colorist and remote DaVinci Resolve systems are required to carry matching timelines, and the clip count, the clip durations, and the system resolutions all have to line up. A summary of what a remote grading session needs and where it is limited follows below.

### Requirements for Remote Grading

- The same version of DaVinci Resolve must be installed on both systems.
- Before the remote grading session begins, the Timeline you intend to grade has to be conformed on each

grading session.

- Both the count of clips on the Timeline and how long each clip runs have to match exactly.
- Throughout grading, the remote client system keeps its active Timeline and versions continually

updated. Building, removing, or swapping the Timeline on the client’s DaVinci Resolve is forbidden. Should you do it, the remote grading session ends at once.

- No grading tweaks can be made at the remote client’s DaVinci Resolve workstation until the remote grading session is over.

NOTE: Remote grading does not require a shared project library.

### Setting Up for Remote Grading

For a remote grading session to begin, the client’s DaVinci Resolve has to reach the colorist’s system over TCP/IP. 1 On the remote client’s workstation (the machine that gets driven from afar), launch DaVinci Resolve, sign in, and bring up the project slated for remote grading. 2 From that same remote client’s workstation, choose Workspace > Remote Grading (Ctrl-G). Up comes a window bearing text fields for typing the colorist system’s IP address and port number. 3 Put the IP of the colorist’s DaVinci Resolve workstation into the IP address field. Where the colorist’s system already holds a public IP address, you can leave the port number at its default value (15000). Where the colorist’s system sits on a private network, the colorist or their network administrator ought to point the port number at one on the public IP router that routes internally to port 15000 of the colorist’s DaVinci Resolve. 4 As soon as the remote client clicks Connect, the client’s DaVinci Resolve system tries to open a connection to the remote colorist’s workstation.

5 After the connection comes up, the colorist sees a pop-up asking whether to permit an incoming Remote Grading connection. 6 Click OK to accept, shrink this dialog window down, and keep grading as usual. The Remote Grading session stays live until one of the participants opts to disconnect, or until some error forces DaVinci Resolve to shut the session down on its own.

### Remote Grading Restrictions

So that the feature can run across a low-bandwidth, possibly high-latency Internet link, certain limits apply to remote operation.

- After playback begins, the two DaVinci Resolve systems can run at differing playback speeds. Only once playback halts are the frame positions assured to be in sync.
- Input/output/display LUTs set from the Config page on the colorist’s DaVinci Resolve have no bearing on the client system; whatever LUTs are chosen on the client’s DaVinci Resolve take over instead.
- Presets set from the Config/Color pages on the colorist’s system have no bearing on the client’s system; whatever Presets are chosen on the client’s DaVinci Resolve take over instead.

### DaVinci Remote Monitor (Studio Version Only)

With DaVinci Remote Monitor, an accompanying application, you gain a low latency, high quality video signal carried over a network for the sake of monitoring, editing, and color grading. As the host works inside DaVinci Resolve, DaVinci Remote Monitor mirrors the output of that host’s Viewer live. That gives producers a way to keep an eye on a session, while editors and colorists get to operate remotely through the DaVinci Resolve interface fed by a data stream off a remote DaVinci Resolve workstation. That data stream is good enough that the signal can be routed through a Blackmagic DeckLink or UltraStudio device to a grading monitor with the same trust in the output you would place in a local connection. You can tune the stream quality to suit your specific requirements and whatever bandwidth you have. For offline editing an editor, say, might get by with just an HD h.264 8-bit 4:2:0 codec, whereas grading HDR could oblige a colorist to use the full UHD h.265 12 bit 4:4:4 RGB codec. NOTE: To keep things clear throughout this section, the central DaVinci Resolve workstation sitting in the post house or data center and pushing out the video gets called the “Resolve Host,” and whatever gear takes in that stream gets called the “Resolve Clients.” In practice, though, every one of these is simply a device running the same version of the DaVinci Resolve Studio together with the DaVinci Remote Monitoring apps.

### Requirements for DaVinci Remote Monitor

Dependably moving a high-quality video signal from one machine to the next brings a few hardware and software constraints and prerequisites that fall on the Host and Clients. For DaVinci Remote Monitor, the Resolve Host has to satisfy these hardware and software requirements:

- On the Resolve Host there must be an installed copy of the Mac, Linux, or Windows build of

DaVinci Resolve Studio.

- On Linux and Windows the Resolve Host requires that an RTX series NVIDIA GPU

with its drivers be present. AMD and Intel GPUs are currently unsupported.

- The Host must have a Blackmagic Cloud account.

For DaVinci Remote Monitor, the Resolve Client has to satisfy these hardware and software requirements:

- On the Resolve Client there must be an installed copy of the Mac, Linux, or Windows build of DaVinci Resolve

Studio. The DaVinci Remote Monitor App lands automatically in the same folder as DaVinci Resolve.

- As Client platforms, Apple iPhone and iPad devices are supported. Grab the DaVinci Remote Monitor app off the App Store (those devices do not require the Studio Version of DaVinci Resolve).
- On Linux and Windows the Resolve Client requires an RTX series NVIDIA GPU plus its drivers. AMD and Intel GPUs are currently unsupported.
- All Clients must have a Blackmagic Cloud account.

### Setting Up DaVinci Remote Monitor

Getting a Remote Monitor session going is easy from within the DaVinci Resolve Studio interface; beyond that, the Host along with each Client has to hold Blackmagic Cloud accounts. To begin a DaVinci Remote Monitor session while acting as the Resolve Host: 1 Have the Resolve Host run the complete DaVinci Resolve Studio edition of the program. 2 Select Workspace > Remote Monitor. 3 If needed, sign into your Blackmagic Cloud account. 4 Within the Remote Monitor Window, choose the Video Codec along with the Bitrate you plan to use this session. Keep in mind your chosen Video Codec must be supported by every client device. When broad compatibility is the priority, H.264 4:2:0 8-bit serves well, yet exact color monitoring may demand some other 10- or 12-bit codec in its place. As additional clients connect, the bandwidth required rises. Running Remote Monitoring over the internet is feasible, although a wired ethernet connection yields the best results.

The DaVinci Remote Monitor Session Setup 5 Tick the “Automatically accept connections” box so that anybody holding the Session Code can join straight away. Leave that box unticked if you would rather approve every connection by hand. 6 Click the Start Session button. 7 Copy the generated Session Code out of its field, and pass it along to all the Resolve Clients by email, text message, and so on. Your Remote Monitor is now up, and a timer reports how long the current session has run. Down in the lower right of the DaVinci Resolve interface a Remote Monitor icon appears, and the top of that icon turns red once at least one Client has joined and you have gone “live.” Who is presently connected as a Client is shown in a Session Participants field.

The DaVinci Remote Monitor showing the time connected and the participants involved

To join a DaVinci Remote Monitor session while acting as a Resolve Client: 1 Have either the complete DaVinci Resolve Studio edition installed on the Resolve Client, or else the iOS app. 2 Fire up the DaVinci Remote Monitor app on whatever device you are using. It sits inside the DaVinci Resolve folder on the machine that received the software install. 3 Log into your Blackmagic Cloud account. 4 Drop the Session Code the Resolve Host gave you into the field provided. 5 Choose whichever Output Device you wish to monitor through. That could be a connected computer display, or a Blackmagic Decklink or UltraStudio device when you need color accurate monitoring. 6 Click the Join button.

### The DaVinci Remote Monitor app Join screen

Your Remote Monitor window now opens, letting you watch and listen to whatever sits in the Resolve Host’s current viewer as that person works. NOTE: To set up connections between DaVinci Resolve Studio and several clients, Remote Monitoring relies on WebRTC. That said, certain tightly locked-down network arrangements might still stop a session from starting, in which case a VPN could be needed. For top performance a wired connection is advised. To finish a DaVinci Remote Monitor session while acting as the Resolve Host: 1 Click the DaVinci Remote Monitor icon down at the lower right of the interface. 2 Press the End Session button to shut the Remote Monitor down for all users, or click the X beside any Client’s name to cut that one user’s session. To Leave a DaVinci Remote Monitor session as a Resolve Client: 1 Bring the DaVinci Remote Monitor app to the front (rather than the Remote Monitor window). 2 Press the Leave button to wrap up your session.

To switch the Codec and Bitrate partway through a DaVinci Remote Monitor session while acting as the Resolve Host: 1 Click the DaVinci Remote Monitor icon down at the lower right of the interface. 2 Up at the upper right of the Remote Monitor window, click the Settings icon. 3 Choose a fresh Codec plus a fresh Bitrate for the video stream. 4 Press the Save button. Doing so switches the streaming settings over to the new codec and bitrate you selected. Clients already attached are reconnected to the new stream automatically, with nothing required of them on their side. That gives you an easy way to adjust the video stream’s quality mid-session to work around bandwidth and hardware troubles.

### DaVinci Remote Monitoring Using IP Address Connections

There is also the option of running Remote Monitoring over plain IP Address Connections rather than logging in through Blackmagic Cloud. Taking that path, however, asks for a little technical skill in getting your network set up properly. Setting up Remote Monitoring over IP connections on the Resolve Host Walk through what follows to get your host grading computer ready for others to monitor. 1 Confirm that you have signed out of Blackmagic Cloud under Preferences > Internet Accounts. 2 Under Preferences > System > General, tick the box labeled “Use Remote Monitoring without Blackmagic Cloud.” 3 Select Workspace > Remote Monitoring. 4 Dial in the codec and bit-rate parameters however you prefer, then click Start Session. 5 Pass along to every client the IP Address or set host name belonging to the Resolve host. Setting up Remote Monitoring over IP connections on the Resolve Clients Walk through what follows to get your client computer ready for keeping watch on the host’s workstation. 1 Launch the DaVinci Remote Monitor application. 2 Within the Remote Monitor setup dialog, pick “Use Remote Monitor without Blackmagic Cloud.” 3 On the iOS or iPadOS versions of the App, head to the iOS Settings > DaVinci Monitor, then switch on “Use Remote Monitor without Blackmagic Cloud.” 4 Type the Resolve host’s server IP Address or Host Name into the Host field. 5 Click Join. To operate this mode you will need to configure firewall exceptions and the proper port forwarding yourself. Starting a session and taking connections proceeds exactly as before. For its traffic this mode relies on TCP server port 16410 plus, per client, TCP/UDP port 16411, 16412, etc.

Where the Use Remote Monitor without Blackmagic Cloud settings live across the computer and iOS versions

### DaVinci Remote Monitoring via User Specified TURN Servers

For teamwork across intricate network-security arrangements that clamp down on the WebRTC STUN protocol, you can now opt to put self-hosted or cloud-based TURN servers in charge of routing and relaying the monitoring streams. To turn this on, tick the box at Preferences > System > General > Use TURN server for Remote Monitoring. Then supply the URL of your own TURN server.

### DaVinci Remote Monitor Restrictions

A handful of limitations on the DaVinci Remote Monitor application are worth keeping in mind at the moment.

- Over an internet link, limited bandwidth can drag performance down. Should the bandwidth sink too far or drop out altogether, the Host disconnects and shows an error message.
- For now, the only pages where DaVinci Remote Monitor functions are Media, Cut, Edit, Color, and Deliver.
- Currently Audio is limited to only 2 channels.
