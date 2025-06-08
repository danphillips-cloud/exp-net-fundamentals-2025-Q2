
## Firewall Rules Testing Locally

When attempting to test Firewalls locally, I found that it was hard to test using localhost because Firewall rules will not block on the same network. I needed to attempt access to the network on the different machine. 


## AWS Windows Server, Serving Simple Website

I was able to start a web server using python to serve a single static page

The firewall rules block everything that doesn't have an inbound rule. 

I added an inbound rule for port 8000. From my local machine I used CURL and was able to access the server. 

I also have to remember to open port 8000 on the AWS Security Group, giving acess to only my IP. 



![](./assets/win-firewall.png)