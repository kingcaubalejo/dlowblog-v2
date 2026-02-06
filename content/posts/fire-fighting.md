---
author: "dlowrenz"
title: "Fire fighting after NS transfer: A crazy one."
date: "2024-02-06"
description: "Fire fighting after NS transfer: A crazy one."
tags: [
    "markdown",
    "text",
]
---

## I became a fire fighter.

We had a task to transfer our new website designed in Wix to our current domain. So Wix is a CMS tool for me; it has NS (nameservers) and other domain-related stuff. Our architecture is like this: we have the domain www.mydomain.com, which has multiple subdomains attached to it. Everything was working fine until we transferred the nameservers of Wix to our domain hosting.

## But let me narrate how a DNS works.
DNS is like the internet's address book. When you type a website address (like google.com) into your browser, your computer needs to know the corresponding IP address (like 192.0.2.1) of the server where that website is hosted. Here's how it works:

**1. Request Initiation:** Your computer sends a request to a DNS resolver (like your internet service provider's DNS server) asking for the IP address associated with the domain name you entered.

**2. DNS Lookup:** If the resolver knows the IP address already, great! It sends it back to your computer. If not, it starts a series of lookups.

**3. Recursive Lookup:** The resolver may have to ask other DNS servers. It starts with the root DNS servers, then moves to the top-level domain (like ".com"), then the authoritative DNS servers responsible for the specific domain (like "google.com"). Each step narrows down the search until it finds the IP address.

**4. Response:** Once the resolver finds the IP address, it sends it back to your computer.

**5. Caching:** To speed up future requests, your computer and the resolver might cache the IP address for a while so they don't have to go through the whole process again.


By the way, we are using GoDaddy, and everything there seems to be easy. I led the transfer alongside my manager, who was there to witness the procedure. However, after some time, we experienced an outage. A fire was burning our APIs. The funny part is that we did it without thinking that it is Business as Usual (BAU). In short, we have live users. Brave, so brave. I quickly ran through our DNS, which is with GoDaddy, and reverted back all the changes. But since the issue here is DNS, I had nothing else to do but wait for it to finish resolving for other users. Going through this left me with a bunch of valuable lessons.

#### Lesson Learned

* Don't do anything silly if it is in BAU (Business As Usual).
* Check the traffic of the domain before doing anything crazy.
* Involve more eyes in the change.


It seems like everyday is day to learn new things.

{{< css.inline >}}
<style>
.canon { background: white; width: 100%; height: auto; }
</style>
{{< /css.inline >}}
