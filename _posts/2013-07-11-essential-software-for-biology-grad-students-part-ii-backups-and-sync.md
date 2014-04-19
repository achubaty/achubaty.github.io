---
layout: post
status: publish
published: true
title: ! 'Essential software for biology grad students: Part II Backups and Version
  Control'
author: Alex Chubaty
date: !binary |-
  MjAxMy0wNy0xMSAwOToxMzo1MiAtMDcwMA==
date_gmt: !binary |-
  MjAxMy0wNy0xMSAxNjoxMzo1MiAtMDcwMA==
categories:
- Software
tags: []
comments: []
---

## Always. Back up. Your data.

Simple, yet for various reasons many people simply don't. Backing up data and documents is critical in the event of random computer (or, more likely, user) failure. *Losing your data sucks.* I have seen too many frantic colleagues try to get at data on a failed hard drive: many had some (but not all) of their most important data backed up, but others were left with few options and resorted to spending hundreds of dollars on data recovery assistance.

Unfortunately, even when people do attempt to make (and regularly use) backups of their data, they either don't backup everything or they backup so infrequently that they end up losing a day's, or a week's, or even a month's worth of work. So in order for a backup regimen to actually protect your data, the key is to **1) backup everything**, and **2) back up often**. I'll also add that you should **3) keep a remote copy** in the event that something happens to your primary backup.

Ideally, a backup solution will deal with all three of these points, and I'll discuss some options below.

### External hard drives or USB drives

Hard drives are cheap, and the storage capacity of portable external hard drives is huge. You can buy a 2TB external drive for under $100. So, for relatively low cost, you can effectively back up all of your data (music and movies included) to and external hard drive and be done with it, right?

Not quite. The problem with using an external hard drive is that you need to remember to plug it in and backup your computer at least once a day in order to keep your backups current. Not only that, but you will also need to ensure you have a remote copy somewhere in case you lose or damage your external hard drive.

### Network Attached Storage

I like NAS devices because, like external hard drive they aren't too expensive, yet they overcome the limitation of having to remember to manually initiate backups. Basically, a NAS device plugs into your router and sits on the network, allowing you (or others on your network) to access the files stored. All you need to do is configure your computer's operating system to backup to the NAS, and voila! If anything happens and you need to restore from backup you simply tell your computer to restore from the NAS.

The downside is that your backups will only run when you are connected to the network on which the NAS resides. So if you go away to a conference for a few days, or you have a super-productive day at school, you'd better make sure nothing happens to your data before you get home to backup the work! You'll also need to keep a remote backup copy handy.

### Email

One way of ensuring you have a remote copy of your work is to email it to yourself. This works fine once in a while, but if you were to email every file to yourself every time you made changes, you'd likely fill up your inbox or go crazy. Plus, something will probably slip through.

### University FTP Server

I should probably mention that most Universities do provide online storage for their students - usually a couple gigabytes' worth - that is accessible over FTP or similar. It's worth checking out, even if it doesn't give you much storage space.

### The Cloud

In the last several years there has been a huge increase not only in the number of online cloud storage providers but also a increase in the amount of free storage space they offer their users. These cloud storage providers offer a desktop client that runs on your computer and continuously monitors changes to files, which are then uploaded to the storage servers. Thus you can hit all three "must haves" with these services: your files all get backed up, in real time, and you maintain remote copies of your data.

I personally use <a href="http://www.dropbox.com">Dropbox</a>, but other options include <a href="https://one.ubuntu.com/">UbuntuOne</a>, <a href="https://spideroak.com/">SpiderOak</a>, and others. These services give you several GB worth of online storage and allow you to keep your files synchronized across multiple computers, and can also be accessed via web interface. These cloud storage providers give you more space with a paid account, but with Dropbox at least, I get additional space for signing up with an educational email address and for every referral I make (the referee also gets bonus space). Space hasn't been an issue for me.

The other awesome feature of Dropbox is that it provides <em>version control.</em> Using the web interface, you can view previous versions of your files, and also roll back changes to restore previous versions or undelete things from your Dropbox. It also provides good collaboration options, allowing you to create shared folders for group projects.

**One warning:** BC Privacy Legislation prohibits storing personal information on non-Canadian servers. This means that, for example as a TA or instructor, you can't store student grades etc. using cloud storage, because the servers are located in the USA.

### Summary

Overall, the easiest way to have automated backups is to use a cloud storage provider like Dropbox. Although the free plans have limited storage space, the limits are easily increased. Besides, you can't beat "no fuss" when it comes to backing up your work! However, in practice I do use some combinations of the other backup methods, depending on the type of data and how much there is to move between computers.

## Version Control

As mentioned above, some cloud storage/backup providers offer version control, which allows you to view and revert changes made to your files. Dropbox certainly does a good job at this, and the undelete feature has saved me on several occasions. However, the main drawback of Dropbox's version control is that it operates on a *per file* basis.

Often when writing papers (or code), I trash or substantially rewrite something, only later to realize that what I overwrote wasn't that bad. Hitting ctrl-z will undo the changes, but it also means it will undo any progress you've made. Restoring previous version of your document using Dropbox will get you an old copy, but you still have to hunt around to find exactly which version you want to restore. And what if you actually want to incorporate changes from multiple restored files?

This is where "real" version control software (VCS) comes in handy. Now, I'm new to the VCS game, having only started using <a href="https://github.com/">Git</a> this year, but already I can see its power and potential. If you're working with text files - be it a paper written in Markdown (maybe LaTeX), or chunks of code - you will want to use Git.

This post has run rather long, so I won't be providing a "how to", but <a href="https://github.com/">GitHub</a> provides great help getting started. You don't *need* to use GitHub at all to use Git - you can keep everything local (in a Dropbox folder!) and still have access to all of your project files. Try it. Use it.

