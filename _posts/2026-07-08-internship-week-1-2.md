---
layout: post
title: "Internship Log - Week 1-2"
date: 2026-07-08
category: internship
tags: ["internship", "grc"]
excerpt: "First two weeks as a GRC intern"
---

## Introduction

I started my internship on 29th of June as a GRC intern at a bank with the goal of gaining practical experience in information security, governance, risk and compliance. I became interested in GRC after I took a course on Governance in my university. It just clicked. Planning everything out, determining where things can go wrong before you even start doing it, mitigating risks. Moreover, I will be communicating with other departments, understanding their processes and learning how the company works in general, which helps me get better at entrepreneurship, my ultimate goal.

Before starting my internship, my background was mostly in software engineering, system administration, deployment and offensive security. While I had an understanding of security concepts, I had limited practical experience with GRC work, especially in a banking environment, where the stakes are high.

I landed the internship through referrals. The application process consisted of an interview with HR and another technical interview with some of my current coworkers. 

It's worth mentioning that I signed a non-disclosure agreement (NDA) and can not get into too much detail.

## Week 1 - Onboarding

The first week was mainly about becoming familiar with the organization and the tools used by the GRC team. I received access to necessary systems, and internal documentation. I also read through the bank's security policies and the GRC playbook. The amount of terminology and documentation made the first week somewhat challenging. 

I also worked with teammates to resolve internal tickets. This was useful because it allowed me to observe how the team communicates and handles day-to-day GRC tasks. When I was unsure about a process or the meaning of something in documentation, I could ask teammates for clarification. 

## Week 2 - First Task

During my second week, I developed an internal AI-based knowledge retrieval solution (RAG) that uses the bank's internal legal acts.

This task was interesting because it connected my existing technical skills with the GRC knowledge I was beginning to develop. I already had experience with programming, which gave me a solid starting point. I still learned a lot about AI engineering, LLMs, RAG systems, and fine-tuning. 

A major challenge was resource limitation. Indexing vectors, running BM25 algorithm on said vectors (400+ legal documents) on every call and local LLM output speed was not satisfactory and took more time than it should have. Another challenge was that the documents were in azerbaijani, which is a morphologically complex language.