---
title: 'Why I Built IP Analyser: Making Traffic Easier to Understand'
description: 'A Drupal contribution inspired by customers trying to understand the traffic behind their views and visits consumption.'
pubDate: 'Nov 01 2026'
category: 'Open source & practical tools'
---

One customer question that motivated me to build IP Analyser was about consumption: when a subscription uses a views-and-visits model, what is driving the traffic behind that usage?

A total can tell a customer that activity increased. It does not necessarily tell them where to investigate. They may want to know which IP addresses are making many requests, which paths receive that traffic, and whether a browser or automated client appears to be involved.

I wanted to help make those questions easier to explore within Drupal.

## From access logs to a clearer starting point

[IP Analyser](https://www.drupal.org/project/ip_analyser) is my Drupal open-source contribution. It turns uploaded Apache access logs into reports that can be explored by IP address, user agent, path, and date.

The coding task connects several steps: reading log records, extracting useful fields, aggregating request counts, and presenting the results in a form that helps someone investigate. That is a practical example of using code to make existing operational information easier to understand.

The module works with existing logs inside Drupal rather than acting as an external analytics service or a real-time visitor tracker.

## A hypothetical investigation

Imagine a customer notices an increase in reported consumption. They review logs from the relevant period and find that a small number of IP addresses account for a large share of the recorded requests.

That finding creates better questions:

- Which paths are those addresses requesting?
- Is the activity concentrated in a particular period?
- What user agents are recorded?
- Is it expected activity, such as a crawler or an integration, or something that needs further investigation?

This is an illustrative workflow, not a claim about a particular customer’s results. A high request count alone does not establish that an IP address is malicious or should be blocked. A shared address can also represent multiple users.

## Traffic evidence is not an invoice

The motivation comes from consumption questions, but access-log request counts are not automatically the same as billable views or visits. The hosting provider’s measurement rules and the scope of the logs need to be considered before making a billing conclusion.

I describe IP Analyser as an investigation aid: it helps customers understand recorded traffic patterns and decide what to examine next. It does not independently calculate exact subscription charges or guarantee savings.

That distinction matters when explaining a tool. Useful reports should help a customer make a better-informed decision without promising more certainty than the data provides.

## Why this project matters to me

Support gives me a close view of the questions customers struggle to answer. Building IP Analyser is a way to turn one of those questions into something others can use and improve.

It also reflects the kind of engineer I want to become: someone who investigates the immediate problem, looks for a reusable improvement, and shares the work back with the community.

If you try the module, I would be interested in the question you hoped the report would answer—and what would make that answer clearer.

[Explore IP Analyser on Drupal.org](https://www.drupal.org/project/ip_analyser).
