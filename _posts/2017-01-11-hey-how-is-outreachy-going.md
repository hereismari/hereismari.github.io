---
title: Hey, How is Outreachy going?
author: Marianne Linhares
header-img:
date: 2017-01-11
tags: [Post, Outreachy, OpenStack, Sahara]
layout: article
---

# Hey, How is Outreachy going?

Hey there! First of all sorry for the absent time without writing on the blog (especially not writing about Outreachy), but anyway... Happy 2017, and we're back on track! So, the [last Outreachy post](https://mariannelinhares.wordpress.com/2016/12/17/running-mapreduce-jobs-with-devstack-using-manila-swift-and-hdfs-as-data-sources-tutorial/) was about how to run a MapReduce job using DevStack and different types of data sources as input and output. In this article, I'm gonna talk a little about the things I've done until now in this internship and what I'm currently doing. As[ I said before](https://mariannelinhares.wordpress.com/2016/12/10/welcome-to-outreachy/),  my internship project is to refactor some data source/job binary related code in order to create a clean abstraction that will allow new developers to implement new data source types and job binary types more easily. So, how are things until now?

  1. My first task was to learn a little more about [stevedore and how Sahara uses it](https://mariannelinhares.wordpress.com/2016/12/10/what-is-stevedore-and-how-is-it-related-to-sahara/)
  2. Then I've set up the DevStack environment in order to run MapReduce jobs and to learn how to do that with multiple types of data source (just in order to understand how the final user does it)
  3. One of the major tasks I had to do was to create the abstraction itself, it demanded a lot of coding reading and grepping code all over the Sahara repository. The result of this task was the creation of the [spec](https://review.openstack.org/#/c/415339/) and [blueprint](https://blueprints.launchpad.net/sahara/+spec/data-source-plugin) of the project. These are still being improved accordingly with task 4.
  4. Develop the abstraction and the data source/job binary types implementation, and of course, refactor the code in order to adapt for these abstractions. This is what I'm currently working on and the code can be seen [here](https://review.openstack.org/#/c/416359/).

I hope this post was helpful somehow, have a nice day!
