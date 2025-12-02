# Retro Game Server.
A final project for CSCI 4345

## Explanation of the Project
For this project, I created a remote retro gaming server using an old laptop running Ubuntu. The goal was to configure a system that allowed another user to connect over the network and play games through game streaming technology. The system required setting up an operating system, installing emulation software, configuring a game streaming server, resolving network issues, and successfully establishing a peer to peer remote gaming session.
The final result was a fully working RetroArch + Sunshine streaming setup where a remote client connected through Moonlight and was able to play games hosted on my machine.

## Breakdown of Your Implementation

### Network Topology
-	Server: Old laptop running Ubuntu (fresh installation).
- Local Router: Spectrum modem/router (restrictions on public IP and port forwarding).
-	VPN Mesh Network: Tailscale used to bypass public IP and port forwarding limitations.
-	Client: Friend's computer running Moonlight.

  This setup created a virtual private network between the two devices, allowing direct encrypted communication using Tailscale assigned IPs.


## Configuration Details

1. Ubuntu Installation
  -	Wiped the laptop and removed Windows completely.
  -	Installed Ubuntu from a bootable USB.
    
2. RetroArch Setup
  -	Installed RetroArch using Ubuntu package manager.
  -	Added BIOS files and ROMs to the proper directories.
  -	Configured RetroArch controllers, video, and core settings.
  -	Tested gameplay locally to confirm proper emulation.

3. Sunshine Setup
  -	Installed Sunshine (open source NVIDIA GameStream compatible server).
  -	Configured a Sunshine application entry to launch RetroArch.
  -	Verified Sunshine was running and accessible.

4. Network Configuration Issues
  -	Initial connection attempts failed because Spectrum's router does not allow modifying certain network settings, including port forwarding.
  -	Public IP was not reachable externally.

5. Tailscale VPN
  -	Installed Tailscale on both server and client.
  -	Created a Tailscale mesh network.
  -	Used the Tailscale assigned private IP as the Moonlight connection address.
  -	Verified that the peer showed up correctly in the Tailscale admin console.


## Communication Flow

1.	Sunshine hosts a game streaming server on the Ubuntu laptop.
2.	Tailscale creates a direct VPN tunnel between the laptop and the client.
3.	Moonlight connects to Sunshine using the Tailscale private IP.
4.	Game-stream video/audio streams from Sunshine → Moonlight.
5.	Controller input sends back from Moonlight → Sunshine.
6.	Remote user plays RetroArch games in real time.


## Tools and Technologies
-	Ubuntu Linux (OS)
-	RetroArch (Emulator)
-	Sunshine (Game streaming server)
-	Moonlight (Client application)
-	Tailscale (VPN mesh networking)
-	Spectrum Router (with limitations that required VPN workaround)

## Demonstration
### The demonstration included:
-	Screenshots of Ubuntu installed.
 
-	Installing RetroArch
 

-	RetroArch Installed


-	Sunshine Installation
 

-	Sunshine Installed and running 
 
 
 
-	Tailscale Installation


-	Showing assigned IP.
 

-	Friend Showing connection to mesh
 

-	Friend Showing he is unable to connect to Server
 
-	Friend Showing is accessible now
 
 
-	Video recording of the remote gaming session.

<video src="videos/Gameplay-1.mp4" width="320" height="240" controls></video>



The remote gameplay session was successful—my friend was able to connect using Moonlight and play a game streamed from my Ubuntu laptop.


## Citations
### Software Download Pages
-	RetroArch – https://www.retroarch.com
-	Sunshine – https://app.lizardbyte.dev
-	Moonlight – https://moonlight-stream.org
-	Tailscale – https://tailscale.com
-	Ubuntu – https://ubuntu.com/download
### Documentation Used
-	RetroArch documentation
-	Sunshine server wiki
-	Tailscale setup guide
### YouTube Tutorials
-	Ubuntu installation walkthroughs
-	RetroArch configuration videos
-	Sunshine + Moonlight setup tutorials

