---
Title: Creating a Redis Enterprise Cloud Subscription
description: 
weight: $weight
alwaysopen: false
---
## What is a Subscription?

A Redis Enterprise Cloud subscription consists of a selected cloud
provider (and respective region, e.g. "Azure - US Central"),
architectural model, memory limit and feature set. You can have multiple
subscriptions in different providers and regions, all easily managed
from a single console.

## Creating a Subscription

1.  Navigate to Subscriptions using the menu in the top right corner of
    the page.
2.  Click on the plus sign below the Subscriptions section of the page.
3.  Select your preferred Cloud Provider and region for your databases
    to be created in.
4.  Create a subscription name. It will appear in the list of
    subscriptions so you can easily tell them apart.
5.  Select from three types of plans:
    -   Cache plans do not include replication or persistence of data.
        In the event of a failure, new resources are immediately
        available with no change to your endpoint.
    -   Standard plans can have a diverse set of features including
        in-memory replication, auto-failover, data persistence, and
        backups. Selecting this option will double the memory size of
        your dataset.
    -   Multi-AZ (Availability Zone) plans offer all the benefits of
        Standard plans, as well as auto-failover and in-memory
        replication to another availability zone. Memory size - select
        from 30MB (free) to 5GB (\$33/mo), or a flexible pay-as-you-go
        model.
6.  You can have multiple databases within a plan, but the combined size
    cannot exceed the plan's memory limit. For unlimited sizes, try the
    Pay-As-You-Go plan. Click on a memory size to view its respective
    features.There are three types of memory size plans to choose from:
    -   **Free:** The free 30MB plan is and continues to be free, as
        long as you continue to utilize it. Utilization is defined as
        connecting to and issuing commands to the database during a
        one-month period.
    -   **Fixed size:** There are fixed-size subscription plans ranging
        from 100MB to 5GB. In these plans, the combined memory usage of
        all databases using this plan will be capped by a fixed limit
        for which you pay a fixed amount each month.
    -   **Pay-As-You-Go:** This plan makes all features available and
        accommodates unlimited database scaling. You can estimate your
        costs using the usage calculator that appears at the bottom of
        the page when you select this plan.
7.  Click the "continue" button to [create a
    database]({{< relref "/rc/administration/setup-and-editing/creating-databases.md" >}}).
