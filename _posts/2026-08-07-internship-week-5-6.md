---
layout: post
title: "Internship Log - Week 4-5"
date: 2026-08-07
category: internship
tags: ["internship", "grc"]
excerpt: "Third two weeks as a GRC intern"
---

## Week 5 - Serious findings

During week 5, the workload was relatively light. I resolved some tickets here and there, but I was idle for the most part. One of the responsibilities of the GRC division was monitoring data loss prevention (DLP) logs, and holding violators accountable. 

For background, every employee gets a corporate laptop that is monitored. The DLP software was solid, but it made me think: what if it has blind spots? After all, it is more-or-less our responsibility to minimize data leak. The computers are pretty restricted: no admin access, unable to run executables, powershell scripts, etc. If an employee needs a certain software, there is an internal app marketplace, where they can install whitelisted software, no questions asked.

There were popular IDEs in this app store, some of which come with extensions marketplace. It seemed like a good place to start. I quickly noticed that all extensions are available to download, so I installed a real-time collaboration extension on both my corporate and personal laptop which was outside corporate network. I even created files with dummy personally identifiable information (PII) that should've been caught by DLP software upon transfer. Needless to say, I successfully "exfiltrated" confidential data. This was a serious finding and motivated me to look for other ways data loss could happen.

So I reverse-engineered the thought process. Why was I successful in this attempt of mine? I realized the collaboration was taking place through an encrypted HTTPS tunnel, so the software couldn't read the packets and block the connection. Since it's unreasonable to block https connections based on a whitelist, that's what I aimed for next. 

I developed a simple file upload website of my own. Created two almost-identical python scripts that encrypt and decrypt files respectively. Encryption script on corporate laptop, decryption on personal. You can probably see where I'm going with this. It ended up working.

I discovered two different ways to exfiltrate classified documents in one week.

## Week 6 - IT Risks 

The workload was still light during week 6, so I took tasks from another division in Information Security department, namely IT Risks. I was asked to find risks in release management and CI/CD pipeline. I read through the relevant pages on knowledge base and created a list of risks. 3 high, 8 medium and 4 low severity. I was impressed by my own findings.