 Some time ago, I realized that I knew little about VPN, and since it's everywhere, I thought I should gain more knowledge about it. This post is a wrap-up of what I've learned.

# what is a vpn
As [Wikipedia](https://en.wikipedia.org/wiki/Virtual_private_network) says:

> A virtual private network (VPN) is a mechanism for creating a secure connection between a computing device and a computer network, or between two networks, using an insecure communication medium such as the public Internet.

Which, in my understanding, is a way in which computers outside a private network can connect to it. Thanks to this technology, we don't have to be connected with a wire or to the local Wi-Fi to have access to the local network.

VPN can be used in various cases, like: 
- connecting to the company's network while working remotely, thus accessing its resources in a more secure and private way, 
- changing the way services see your location, which can be used for accessing content outside your country, 
- hiding your web traffic from your ISP, - hiding your IP from online services.

# how it works
Normally, data is sent through the internet in packets, these packets are made out of layers. We have a data layer wrapped into a transport layer, a transport layer wrapped into an Internet layer, and eventually an Internet layer wrapped into a link layer.

![[../images/packet.png]]


But when we are using VPN, we wrap these packets into additional transport and Internet layers with the IP of the network to which we are connecting or the device that connected to this network. After proper encryption and making sure that this packet is sent securely, we can use a VPN. 

![[../images/vpn_packet.png]]
# vpn protocols 
VPN protocols determine how data routes between your computer and the VPN server. They vary, while some prioritize speed, others focus on privacy and security. Examples of most popular are below. 
## OpenVPN
It's used for general purpose, especially when security and privacy are top priorities and is a default protocol used by most paid VPN providers.
### pros
- focused on privacy and security
- **flexible** configuration with the help of config files and plugins
- open source 
- available on Linux, Windows, Android, IOS, macOS, routers and more 
- Communication is managed by [SSL/TLS](https://bankubanku.github.io/2023/tls/) , which is used by HTTPS, so it's **tricky to tell that you are using a VPN,** and because of that, it **bypasses most firewalls.**
### cons
- **complex** setup 
- **slower** than i.e. WireGuard
## L2TP/IPSec
Layer 2 Tunnel Protocol is usually paired with IPsec for security because L2TP itself doesn't provide encryption. These two combined offer decent security and privacy, which is why it can be used for shopping online, performing banking operations, and connecting company branches into one network. L2TP was developed by Microsoft and Cisco. A few articles I've read recommend using it when there is no other choice.
### pros
- **flexible** 
- **reliable**
### cons
- IPsec may have been compromised by the NSA
- as **slow** as OpenVPN
- can be **blocked by firewalls**
## SSTP
Secure Socket Tunneling Protocol is Microsoft's closed source VPN protocol. It uses SSL 3.0 for encryption. Articles I've read say it's mostly used by hardcore Windows fans, VPN providers avoid implementing it, and it should be used if other options fail.
### pros
- quite secure
- cross-platform support
### cons
- closed source 
- privacy concerns because of Microsoft's ownership
- less flexible than OpenVPN 
## Wireguard
It's the newest one on the list. Wireguard is still under development, but it is getting attention from the VPN community and paid providers like NordVPN or Mullvad, which have already implemented this protocol. Although it's hard to implement it in its current state since it isn't finished and VPN providers need to create their own versions of it like NordLynx. It's also popular among enthusiasts.
### pros
- simple code base
- extremely fast 
- free and open source 
- secure 
- works well with mobile devices
- easy setup
### cons
- under development 
- needs a privacy patch 
- it has a lot of room for improvement

# summary 
I had fun learning about VPN, and now I have a perspective on what it can do and how I can use it even without any paid providers. Hopefully, this post will be a good starting point and help someone. :D

## resources 
https://www.youtube.com/watch?v=1mtSNVdC7tM    
https://www.youtube.com/watch?v=mxpHRdO4rDU    
https://blog.ipfire.org/post/why-not-wireguard    
https://privacysavvy.com/vpn/guides/wireguard-vpn-protocol/#h-top-3-vpns-offering-wireguard-protocol-quick-list     
https://openvpn.net/    
https://www.techradar.com/vpn/what-is-openvpn    
https://www.comparitech.com/vpn/protocols/    
https://nordvpn.com/blog/protocols/    
https://www.tomsguide.com/features/understanding-vpn-protocols-openvpn-l2tp-wireguard-and-more      
https://www.makeuseof.com/tag/major-vpn-protocols-explained/      
https://www.privacyaffairs.com/vpn-protocols/     
https://www.howtogeek.com/770807/what-is-the-best-vpn-protocol-openvpn-vs-wireguard-vs-sstp-and-more/     
