---
layout: post
title: "MySQL 'Incorrect key file for table' error"
date: 2012-10-30 02:47
comments: true
categories: mysql 
---

When saving a record to a MySQL table the other day I got the error message "Incorrect key file for table 'mytable'; try to repair it". I am uncertain why the error occured and how to ensure it doesn't happen again in the future but a quick fix for the time being is simple.


##How to repair a MySQL table##

All you need to do is to repair the table by running the following SQL command, where "mytable" is the name of the table that gave the error:

    REPAIR TABLE `mytable`;

You can run this from e.g. the MySQL CLI or phpMyAdmin. From phpMyAdmin select the table, then "Operations" from the navigation tabs in the right frame above the table info; then "Repair Table" from the "Table maintenance" options at the bottom of the page.

##When the table is /tmp/#sql_xxx_x.MYI##

If the error looks like "Incorrect key file for table '/tmp/#sql_xxx_x.MYI'; try to repair it" where it refers to a temporary location on the filesystem, it's likely you've run out of diskspace. Read my follow up post for more information.
