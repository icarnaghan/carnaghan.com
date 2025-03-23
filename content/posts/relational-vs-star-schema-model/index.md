---
author: "icarnaghan"
title: "Relational vs Star Schema Model"
date: 2019-03-04
categories: 
  - "data-analytics"
---

There are two main philosophies that have become prominent over the past several decades with information management pioneered by Bill Inmon and Ralph Kimball. Nagesh & Cody (2005) provide an overview of these contrasting approaches, which are vastly different with their own merits and downsides. Inmon believes in building a large centralized enterprise-wide data warehouse using a relational database. Kimball on the other hand recommends starting by defining data marts (subsets of data around a specific domain, or use case) within a star schema. In order to understand these approaches, it is essential to understand the main differences between a relational model and a star model.

## Relational Database Model

At their core, relational models are built for consistency and the purpose of eliminating redundancy in data collection, that can lead to anomalies and inconsistencies. This is achieved by breaking data into multiple tables and relationships. Take for example a typical store or shop, where a set of sales transactions may include customer and product information. In a relational schema, typically the product and customer details would be separated into other tables reducing repeating entries. Without doing this, we would have a lot of redundancy. Now consider products have categories, departments, models. These data would be further decomposed into other tables. These sets of data (in larger organizations) may be broken down further, for example different department locations, etc.

Here we have solved the problem of redundancy, but what if we want to retrieve core data about a transaction and include information of all the above information. This would involve a number of joins across these tables. Consider we’re dealing with a large enterprise level relational database, this could potentially mean dealing with many tables. Retrieving information may involve complex queries and expertise of the entire model to retrieve accurate results. In addition to this, performance may be reduced by using multiple joins to retrieve data.

## Star Schema Model

In contrast to the relational approach, a star schema offers a flatter design. Rather than separating out data to its most granular level into multiple relationships, a star model is primarily organized around facts and dimensions. Consider the transactions mentioned earlier as facts and customers and products as dimensions. A typical star model will contain these two levels, which greatly simplify design. The downside is of course the redundancy issues we were trying to solve in the relational schema. If the goal however is a top-down approach focused around the efficiencies of reporting and simplification of use, then the star model has the edge over a relational model. The star model is a flatter design than a relationship model, therefore we reduce complexity and get to the data we need in an easier fashion.

Sometimes a star model does require more granularity and more levels than the initial two, this type of configuration is sometimes referred to as the snowflake schema. To summarize, star schemas are flatter than their relational counterparts, their flatter design eliminates the need for entities such as lookup tables, and they are easier to query. They do come at a cost of increased redundancy, however they should be considered a good option in terms of building sets of data for reporting, that otherwise may be complex to produce (or performance hitting with multiple joins) in a relational schema.
