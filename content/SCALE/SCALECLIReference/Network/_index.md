---
title: "Network"
geekdocCollapseSection: true
description: "Introduces the TrueNAS CLI network namespace and provides access to child namespaces and commands used to configure network settings." 
weight: 30
draft: false
book: "SCALECLIReference"
volume: "SCALE"
---

{{< toc >}}



{{< include file="/_includes/CLI/CLIGuideWIP.md" >}}

{{< include file="/_includes/CLI/SCALECLIIntroduction.md" >}}

## Network Namespace

The **network** namespace has seven child namespaces and is based on functions found in the SCALE API and web UI. 
It provides access to network configuration methods through the child namespaces and their command.

You can enter commands from the main CLI prompt or from the **network** namespace prompts.

## Network Child Namespace Contents
The following articles provide information on **network** child authentication namespaces:

{{< children depth="2" description="true" >}}
