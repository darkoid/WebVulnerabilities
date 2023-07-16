# Finding and Exploiting Common Web Vulnerabilities

## Description
This project is demonstration of finding and exploiting common web vulnerabilities like SQL Injection, XSS, Command Injection, Insecure File Upload and more. This project will also contain creating your own home lab with web vulnerabilities to analyse and craft exploit. I hope it helps you in your bug bounty exploitation, webapp pentesting or any other reason for you to learn this topic.

## Requirement

### Hardware Requirement
- 4GB RAM for Virtualisation

### Software Requirement
- Kali Linux (Link: https://www.kali.org/get-kali/#kali-virtual-machines) - can use other OS as well but I'm using this
- Docker.io, Docker-conpose (we'll learn setting up and usage as we go)
- Burpsuite (we'll learn setting up and usage as we go)

## LAB Setup
1. Download web labs via tcm link: [**labs**](https://cdn.fs.teachablecdn.com/NgPnyKOwSfWYuwnX3Lzb)
2. After installation of kali linux vm open terminal
    ```
    sudo apt update
    sudo apt upgrade
    sudo apt install docker.io
    sudo apt install docker-compose
    ```
    Check if tools are installed properly
3. Restart your VM
4. Copy the labs into whatever location you want to store them and do the following command
   ```
   tar -xf peh-web-labs.tar-gz
   cd labs
   sudo docker-compose up
   ```
   The last line of the command runs multiple containers using a single yaml file. You can also run it in background by using `-d` which is detach mode.

   First time it runs, it will take some time downloading some things. Next time you run it though, it will be much faster.
   Once you see the following message you are ready to go -

   ![image](https://github.com/darkoid/WebVulnerabilities/assets/81341961/16ff11c3-b2a9-423d-9b0b-94f6a5b5d088)

6. The final step is to set some permissions for the webserver, this is needed for the file upload labs and the capstone challenge. Do this in seperate terminal tab (Control+Shift+Tab).
   ```
   ./set-permissions.sh
   ```
7. Browse to http://localhost
8. The first time you load the lab the database will need to be initialized, just follow the instructions in the red box by clicking the link, then coming back to the homepage.

> **Note:** At any point you mess up the tables or database of the labs you can just reset it by going to http://localhost/init.php

Check of everything is property installed and running -
![image](https://github.com/darkoid/WebVulnerabilities/assets/81341961/fefda031-31f1-43ad-8251-8af1910ea8ea)

## Docker
Before starting lets learn a little bit about docker and its commands. Docker is an operating system for **containers**. Similar to how a virtual machine virtualizes (removes the need to directly manage) server hardware, **containers** virtualize the operating system of a server. Docker is installed on each server and provides simple commands you can use to build, start, or stop containers.

```
# List all running containers
sudo docker ps -a
# Stop the containers
sudo docker-compose stop
# Removing the containers, it will also list container ID that are stopped
sudo docker rm $(sudo docker ps -aq)
# You will need to restart the labs after removing or stoping the containers
sudo docker-compose up
```

## Burpsuite
It comes preinstalled will kali, if you are on other linux use this [guide](https://www.linuxfordevices.com/tutorials/linux/install-burpsuite-community) from portswigger.
Burpsuite is developed by PortSwigger. This tool serves as an application layer proxy which allows you to capture the requests issued by your Browser. With BurpSuite, you can capture requests, alter them, launch attacks, try put different headers and more!

**How to setup burpsuite?**
Install foxy proxy addon on your browser([firefox](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/)/[chrome](https://chrome.google.com/webstore/detail/foxyproxy-standard/gcknhkkoolaabfmlnjonogaaifnjlfnp)) then select options > add > put title as `8080`, port as `8080` and Proxy IP address or DNS name as `127.0.0.1` > click save. Now whenever you need to use burosuite just fireup the application and select the 8080 title from addon menu.

/// add a gif here for setting up foxy proxy on chrome and firefox///

Or you could just use the browser from burpsuite -
![image](https://github.com/darkoid/WebVulnerabilities/assets/81341961/1280a86c-6ac1-4305-8cbc-cda692b34bb0)

## SQL Injection
SQL injection is definitely the most famous web based attack of all time. Let's first learn a little bit about SQL before getting into its attacks.
```
show databases;
show tables;
select * from users
```

## XSS

## Command Injection

## Insecure File Upload

## Attacking Authentication

## XXE

## IDOR

Recently I found out that in API testing this is called BOLA (Broken Object Level Authorisation) which is [API1](https://owasp.org/API-Security/editions/2023/en/0xa1-broken-object-level-authorization/) on OWASP's **[API Security Top 10 2023](https://owasp.org/www-project-api-security/)**. They just have different names they are actually the same thing. So welcome after this topic you'll have some knowledge on API testing as well.

## Capstone

## Quiz
The peh course section(read on the **Motivation or Credit** heading) has one. So I decided make one here as well. Just answer the questions and check if its correct on [_answers.txt_](/answers.txt) file.

**A. What gets printed?**
1. [ ] It's impossible to know.
1. [ ] 13
1. [ ] Something else.

**B. What is the output of ``take_default_list([1,2,3])``?**
1. [ ] It's impossible to know.
1. [ ] 13
1. [ ] Something else.

## Motivation or Credit
Recently [The Practical Ethical Hacking Course](https://academy.tcm-sec.com/p/practical-ethical-hacking-the-complete-course) on tcm academy updated by adding a new section called **Find & Exploit Common Web Vulnerabilities** which was around 2 hours. Credit goes to [Alex Olsen](https://academy.tcm-sec.com/courses/author/1728995) who also made [Practical API Hacking](https://academy.tcm-sec.com/p/hacking-apis) course which I highly recommend. The videos from PEH were so fun to watch I had to make this project.

## Disclaimer
- Neither the project nor its developer promote any kind of illegal activity and are not responsible for any misuse or damage caused by this project.
- This project is for educational purpose only.
- Please do not use this tool on other people's devices without their permission.
- Do not use this tool to harm others.
- Use this project responsibly on your own devices only.
- It is the end user's responsibility to obey all applicable local, state, federal, and international laws.

## Contribute

- Contributions are welcome and encouraged, provided your code is of sufficient quality. 

- Before submitting a pull request, please ensure that your code adheres to the license under MIT license, or dedicated to the public domain (BSD, GPL, etc. code is incompatible)

- Your pull request should fully describe the functionality you are adding/removing or the problem you are solving. Regardless of whether your patch modifies one line or one thousand lines, you must describe what has prompted and/or motivated the change.

- Solve only one problem in each pull request. If you're fixing a bug and adding a new feature, you need to make two separate pull requests.

- If you're fixing three bugs, you need to make three separate pull requests. If you're adding four new features, you need to make four separate pull requests. So on, and so forth.

## Support this project

- Star on [GitHub](https://github.com/darkoid/pufin)
- Share via [Facebook](https://www.facebook.com/sharer.php?u=https://github.com/darkoid/pufin) and [Twitter](https://twitter.com/share?url=https://github.com/darkoid/pufin)
- [Sponsor via GitHub](https://github.com/sponsors/darkoid) — support open source contributions on a regular basis
- <a href="https://www.buymeacoffee.com/darkoid" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-red.png" alt="Buy Me A Coffee" style="height: 61px !important;width: 217px !important;" ></a>
