---
layout: post
title: "Internship Log - Week 7-8"
date: 2026-08-21
category: internship
tags: ["internship", "grc"]
excerpt: "Fourth two weeks as a GRC intern"
---

## Week 7 - Third Party Risk Management

This week I attended a couple of meetings regarding Third Party Risk Management, or TPRM for short. As the GRC team, we help ensure new vendors meet security requirements and that risk is evaluated before onboarding.

I learned how security questionnaires and criticality assessments fit into procurement, and saw early work on automating parts of that workflow.

## Week 8 - Ticketing automation

I was asked to help explore automation for internal tickets using AI. The GRC team gets multiple tickets a day where context switching and long threads cost time. So my task was to prototype an assistant that summarizes context and highlights points needing analyst attention.

While scoping that work, I questioned whether a restricted access path could be abused for unauthorized remote access. I built a minimal, tightly-scoped proof-of-concept to confirm the concern was real, then stopped and reported it with timeline and scope for remediation. It was a sharp lesson: encrypted egress alone does not equal control, you need layered monitoring and quick analyst triage, and automation must never replace human approval.
