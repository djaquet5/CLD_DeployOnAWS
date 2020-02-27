# Lab 01 - Cloud Computing

Author : Baptiste Hardrick & David Jaquet

## Create an Amazon EC2 instance

- What is the smallest and the biggest instance type (in terms of virtual CPUs and memory) that you can choose from when creating an instance?

- |          | Instance type | Virtual CPUs | Memory   |
  | -------- | ------------- | ------------ | -------- |
  | Smallest | t2.nano       | 1            | 0.5 Gio  |
  | Biggest  | x1e.32xlarge  | 128          | 3904 Gio |

  

- How long did it take for the new instance to get into the *running* state?

  - We didn't measure exactly the **pending** time, but it took between 5 and 10 minutes before the instance state became **running**.

- From the **EC2 Management Console** copy the **public DNS** name of the instance into the report.

  - The **public DNS** name is `ec2-54-224-211-186.compute-1.amazonaws.com`

- Once you have successfully logged into your EC2 instance, run the `hostname` and `uname -a` commands and paste their outputs into the report.

  - You can find below the output of the `hostname` and `uname -a` commands :

    ```bash
    $ hostname
    ip-172-31-47-190
    
    $ uname -a
    Linux ip-172-31-47-190 4.15.0-1057-aws #59-Ubuntu SMP Wed Dec 4 10:02:00 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux
    ```

    

- Try to ping the instance from your local machine. What do you see? Explain. Change the configuration to make it work. Ping the instance, record 5 round-trip times.

  - Nothing happens, That is because the firewall (Security Group) only accepts the `SSH` connections.

  - To successfully ping the instance, we had to change our Security Group by clicking on `modifier les règles entrantes`. Then, we add a rule `Accept all ICMP - IPv4` from all sources.

  - Here is the result of `ping` command

    ![ping](assets/ping.JPG)

- Determine the IP address seen by the operating system in the EC2 instance by running the `ifconfig` command. What type of address is it? Compare it to the address displayed by the ping command earlier. How do you explain that you can successfully communicate with the machine?

  ![ping](assets/ifconfig.png)

  The pinged address was `54.224.211.186`, but the address of the virtual machine is `172.31.47.190`. The first address is the address of the DNS server where our VM is located. The `NAT` will know that we want to access to our machine at the address `172.31.47.190` with its translation table.
  
  The IP address obtained with the `ifconfig` command is the effective IPv4 address of the virtual machine.

## Install a web application

- Below is our Drupal page :

  ![drupal](assets/drupal.png)

- The Elastic IP Address is `54.210.173.133`

-  Why is it a good idea to create an Elastic IP Address for a web site (our web application)? Why is it not sufficient to hand out as URL for the web site the public DNS name of the instance? 

## Create an additional EBS volume and use snapshots

- Here is the Availability Zone of our Instance and Volume :
- After formatting and mounting, we have `XX` of space availabe

## Performance analysis of our instance (optional)

- The URL of the Geekbench results for the EC2 instance and our local machine can be find here

- Here is some information about the EC2 instance

  | Performances score | overall | integer | floating-point | memory |
  | ------------------ | ------- | ------- | -------------- | ------ |
  | Single-core        |         |         |                |        |
  | Multi-core         |         |         |                |        |

- Here is some informations about our local machine

  | Performances score | overall | integer | floating-point | memory |
  | ------------------ | ------- | ------- | -------------- | ------ |
  | Single-core        |         |         |                |        |
  | Multi-core         |         |         |                |        |

- Comparison of the machines

## Resource consumption an pricing

- How much does your instance (including disk) cost per hour? What was its cost for this lab?
  - Response
- If the instance runs continously during the whole month, the total cost will be **sfdsfsd**
- If you buy a 1 TB SSD disk at Digitec it currently costs CHF 289. How much does a 1 TB ESB Volume cost for a month?
  - Response

