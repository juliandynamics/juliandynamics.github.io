---
layout: post
title:  "Introducing Live K8S Security Testing - DVLDB"
date:   2023-09-03 14:05:55 +0300
image:  02.png
tags:   dvldb, kubernetes, security, engineering
---

[DVLDB](https://www.dvldb.com) is an open source tool and catalog meant to kickstart security testing for kubernetes and other platforms by leveraging *D**eployable **V**ulnerability **L**ayers. 

## Why use DVLDB?

Working with clients adopting security tooling, it's common to discuss all the various detections and threats that the tool is built to catch. However, there is generally not a unified way to actually *trigger* these detections. Often, we would write scripts or manually misconfigure elements in order to prove that the tool actually worked.

DVLDB is an attempt to build those triggers using infrastructure as code in a way that organizations can take the code, modify it as needed, and start testing infrastructure and launching intentionally vulnerable code. 

## Storytime: Security engineering

Your organization has bought a host of security tooling, there's been some operational training, but little to no automation yet implemented. Management has indicated that it would be nice to test the detective capabilities regularly inside your kubernetes environment, but the security engineering team does not yet have a unified way of building infrastructure in their security testing environment.

Starting with the detections possible in DVLDB automatically gives the organization a host of possible checks for their kubernetes environment, but more importantly, our organization can use the uniform structure of DVLs to build a testing automation platform out of.

For instance, our security engineering team could take each DVL, deploy the infrastructure, and then query our SaaS or on-prem tooling to check whether an event was detected (hopefully in an automated fashion). Maybe what we do is string together the DVL deploys with a custom script to query our system and serially go through each vulnerable layer. 

## Storytime: Incident Response Testing

Your organization has just recently introduced kubernetes and it's been tough to really train security operations teams how to respond in the case of an attack being detected in kubernetes.

As a red teamer or trainer for security teams at your organization, you could leverage DVL's kubernetes layers in a way that can be used in hands-on exercises. For instance, you could train your incident responders about reacting to a "privileged" container being launched into an environment leveraging the privileged container DVL. Then, after launching the DVL, go through the full investigation process and challenge your team to identify the risks and how they would put together a postmortem. 

## Further Use Cases

There're bound to be many more use cases for an organization of a tool like DVL. Even the simplest use case of knowing "what should I be looking for as misconfigurations and vulnerabilities in my platform" from what's in DVLDB can be massively beneficial to organizations.

Look out for more from DVLDB.
