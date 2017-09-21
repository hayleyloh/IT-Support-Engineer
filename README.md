# IT Support engineer Questions


## How to submit the answers

1. Create a GitHub Account
1. Git Clone this repository to your local machine
1. Remove the current `origin` remote (`git remote remove origin`)
1. Create a new repository under your GitHub account (do **NOT** fork this repository)
1. Follow the instructions to `push an existing repository from the command line...`
1. Create a branch called `add_answers` on your local machine
1. Add answers to this Document (using a simple Text editor), commit your answers to the `add_answers` branch
1. Push your `add_answers` branch to your personal remote `origin`
1. Send a notification to your contact at Honestbee with a link to your repository

If any of the steps above is unclear, please try GitHub user guides first, then ask your contact at Honestbee to clarify. 

The method of submission is part of the test (usage of Git) - but we won't use `forks` or `pull requests`. 

## Questions

1.  A vendor is trying to connect to a server we publicly expose (assume we are not using VPN). When asked for his public IP from which he will be connecting, the vendor provides us with the following IP `192.168.0.100`, what should be our next steps? 

    1.  Include questions we may need to ask to get additional information to ensure this vendor will be able to connect over the public internet to our server. __Note that this vendor is not in our LAN, nor on a VPN with us__.

        > Add follow up Questions here as a bulleted list and add an explanation why you ask each question (what do you expect to receive back)

        1.  To make sure RDP client software is used to connect to the server by vendor. 

            Assuming the server is Windows 2012 R2 and listens on TCP Port 3389, thus RDP client may use to connect to the server. 
        
        2.  To provide the vendor with server IP or DNS name
        
            To provide vendor with server's IP/DNS as the information is missing out in above. 


    1.  Write a PowerShell command (assume Windows 2012 R2) to add a new firewall rule on a single server, allowing incoming connections on port `3389` for `TCP` protocol __limited to the public IP of the vendor only__ (assuming we have the public IP of the vendor)

    ```powershell
    # New-NetFirewallRule -Profile=public -DisplayName "RDP-192.168.0.100-port3389" -Direction Inbound -Action Allow -Protocol TCP -LocalPort 3389 

    ```

1.  How do you list all Computers in an Active Directory Domain using Powershell (output DNSHostname in a table format, no need for `filters` or `SearchBase`)

    ```powershell
    # Get-ADComputer -Filter * | Format-Table DNSHostname

    ```

1.  What could possible troubleshoot tests be for the following output on a macOS machine. 
     
    
    For each step, mention what would be your next step

    ```bash
    $ ping microsoft.com
    PING microsoft.com (23.100.122.175): 56 data bytes
    Request timeout for icmp_seq 0
    Request timeout for icmp_seq 1
    ...
    ```

    Notes:

    -   Local machines in the same network can still be pinged by IP

    ans: the computer is having internet connectivity issue. Try to forget wireless network/eternet port if the computer is connected to Wi-Fi/LAN port.if issue persist, the 
	issue may caused by hardware. 
	 

Thank you for your time.
