# Goal

Use Kamailio as a edge proxy for SIP UDP and Websocket (webrtc in general) for transcoding (only voice) and protect Asterisk Wazo SIP signaling.

This configuration is done for 3 servers:
* Kamailio as a sip proxy server
* Rtpengine as transcoding media server
* Wazo as class 5 server

All of this instance has been natted with this configuration.

My example is running on a private Openstack. So external_ip is a private IP to receive the internet traffic, internal_ip is the traffic between my instances and advertise_ip is my public ip.

# Version

* Wazo-platform: 22.04 (No specific configuration needed)
* Kamailio: 5.4.8 or 5.5 (Please note a patch has been submited by Daniel to fix an issue with multiple contacts and it's needed with this configuration)
* Rtpengine: 10.3.1.7

Kamailio and rtpengine are running on Debian 11 and Wazo on Debian 10.

# Information

To use websocket SIP, i added an nginx in front of my architecture for routing websocket SIP traffic to Kamailio and Wazo API to Wazo. Check the nginx configuration.

# Webrtc

To test webrtc client with Wazo, please use our demo on our github.

    https://github.com/wazo-platform/wazo-webrtc-demo

Thank you to Daniel for his help on this configuration.

Please note, Asterisk user can use this configuration with probably some changes but there is not reason it doesn't works.
