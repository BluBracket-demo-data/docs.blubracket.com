---
title: "IaC checks"
description: "How to setup infrastructure as code (IaC) scanning"
lead: "How to setup infrastructure as code (IaC) scanning"
date: 2022-01-12T02:48:57+00:00
draft: false
weight: 200
toc: true
resources:
  - src:
---

Infrastructure as code (IaC) scanning operates differently from other checks in BluBracket. It runs as a job within the CI tool of your choice, and reports its findings back to BluBracket where you can evaluate any found risks. Despite the different operation model, any alerts related to IaC risks are processed by BluBracket as usual, and trigger messages in Slack for example.

Officially supported CI systems for IaC scanning include:
