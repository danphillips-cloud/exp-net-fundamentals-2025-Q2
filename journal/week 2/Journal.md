## Week 2 issues and pivot

This week was challenging for sure. Due to hardware limitations and time restrictions, I had to think of how to complete some of the work. I decided to take inspiration from week 1 and have a look at my own Mediaserver stack setup and apply some knowledge learned in the class. 

## CML

Cisco makes this quite challening to access and download. After getting the ISO, image and VMWare Workstation, I started to get errors:

Turns out my laptop is not compatible and cannot rum CML due to not supporting VTY-x/EPT

## Mediaserver Stack

I run a similar stack that Beko has. As with most, I run a small BeeLink Mini PC that has windows 11. Currently all the Arrs run as native Windows apps and services and I've wanted to put them in a Containerized setup for a while now.

## Reverse Proxy Setup for Media Server Stack

I decided to use Nginx as a reverse proxy to simplify access to media applications like Sonarr, Radarr, and Sabnzbd, all running as Docker containers.

Nginx listens on port 80 of the host machine (e.g. 192.168.1.100). Instead of exposing each service on its own port (e.g. http://192.168.1.100:8085), all traffic flows through Nginx.

    Path-based routing is used to reach each service:
    URL	Routed To

    http://192.168.1.100/sonarr	Sonarr container
    http://192.168.1.100/radarr	Radarr container
    http://192.168.1.100/sab	Sabnzbd container

The internal service containers are not directly exposed to the network.Nginx forwards requests and responses between the client and each internal service, acting as a reverse proxy.

