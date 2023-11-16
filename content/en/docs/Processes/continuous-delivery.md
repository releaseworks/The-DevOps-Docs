---
title: "Continuous Delivery"
linkTitle: "Continuous Delivery"
date: 2020-02-05
description: >
  Continuous delivery a set of practices that grants the ability to release software reliably and repeatedly.
---
{{% pageinfo %}}
This is a draft.
{{% /pageinfo %}}

<p style="font-size: 0.9rem;font-style: italic;"><img style="display: block;" src="https://farm1.staticflickr.com/33/377155179_ed4c846ec5.jpg" alt="4 by 4"><a href="https://www.flickr.com/photos/87724782@N00/377155179">"4 by 4"</a><span> by <a href="https://www.flickr.com/photos/87724782@N00">Tim McFarlane</a></span> is licensed under <a href="https://creativecommons.org/licenses/by-nc-nd/2.0/?ref=ccsearch&atype=html" style="margin-right: 5px;">CC BY-NC-ND 2.0</a><a href="https://creativecommons.org/licenses/by-nc-nd/2.0/?ref=ccsearch&atype=html" target="_blank" rel="noopener noreferrer" style="display: inline-block;white-space: none;margin-top: 2px;margin-left: 3px;height: 22px !important;"><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc_icon.svg" /><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc-by_icon.svg" /><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc-nc_icon.svg" /><img style="height: inherit;margin-right: 3px;display: inline-block;" src="https://search.creativecommons.org/static/img/cc-nd_icon.svg" /></a></p>

## What is Continuous Delivery

> [Continuous Delivery is the ability to get changes of all types—including new features, configuration changes, bug fixes and experiments—into production, or into the hands of users, safely and quickly in a sustainable way. - Jez Humble](https://continuousdelivery.com/)

Continuous delivery is central to DevOps ways of working, it's goal is to make deployments simple and predictable so they can be done on demand instead of being painful extremely infrequent and highly risky events.

The way this is done is to make sure production code is at all times deployable through a set of techniques the most prominent of which is a deployment pipeline. Most products and tools that are labeled as DevOps tools actually enable continuous delivery.

In this article we'll run through the practices you need to implement continuous delivery and link to subsequent articles on how to implement them.

### Source Code and Configuration Management

Continuous delivery relies on being able to trace the version of your application running in production to the source code that created it, the configuration applied to it and the infrastructure it runs on.

That's why good source code and configuration management is essential for this to work. Source code management has been around for decades, github and it's equivalents are modern software development staples, if you want to adopt a continuous delivery model everything needed to build and run your software must be tracked in some kind of version control system.

What's changed in the last ten years with the growth of api and software driven infrastructure tooling like OpenStack and Amazon Web Services is the ability to manage infrastructure as code. At Releaseworks we advocate heavily for the use of Terraform as a platform agnostic robust infrastructure as code tool that can be integrated seamlessly into delivery pipelines.

Configuration management is now relatively mature and in some implementations of immutable infrastructure has shifted to the infrastructure as code level. But for many projects managing application and server configuration is still extremely important and tools like Puppet and Ansible should be employed to make sure application deployment and configuration is tracked and traceable.

### Continuous Integration

Continuous integration is the foundation on which a deployment pipeline is built. It requires strict version control of everything needed to build the project; code, tests, database scripts, build and deploy scripts.

It must be possible to build, test and deploy in an automated way. Once this has been achieved a server or tool watches your source code management and automatically runs the build and test process when new code is committed to a tracked branch, preferably trunk.

Continuous integration is as much a practice as a technique and requires agreement from the team practicing. For further details see our article on continuous integration.

### The Deployment Pipeline

Continuous integration is often a huge improvement for development teams but it is only one step on the road to generating value. Testing and operations work does not see the benefits with continuous integration and can still have to deal with undeployable buggy software.

By automating your deployment process to production you can get the same benefits in your entire application delivery chain, from development to production as your development team gets from continuous integration. This is the Ops in DevOps as it requires extensive communication and collaboration between Development and Operations teams who have often operated as seperate functions.

It should be made clear at this point that a continuous delivery pipeline does not require that every commit that passes through the pipeline is automatically deployed, there can be a manual approval step and some potential releases may never be released. What it does do is acknowledge that every commit is a potential release and could end up in production.

A deployment pipeline extends your continuous integration pipeline by introducing acceptance testing and the ability to deploy automatically to user access testing, capacity testing and production environments at the push of a button.

By including automating release into production like environments and testing each commit you can increase the confidence that making a change to a production application won’t result in user downtime. Releasing software can move from being a risky event that requires days of planning to a routine piece of work cutting the time from development writing a feature and it rolling out to users.

## Further reading
Include a links on to further reading either within the docs or elsewhere on some of the topics you've covered whether that's shell scripting or something similar.


