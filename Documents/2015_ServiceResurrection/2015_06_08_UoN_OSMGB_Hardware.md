---
title:  'OSMGB hardware meeting 20150608'
author: Anthony Beck, Craig Place, Shaun Hindley
layout: post
category: OSMGB
tags: OSM
bibliography: references.bib
csl: harvard.csl
abstract: |
  Please add in your name to the author list.

  Written using [CommonMark](http://commonmark.org/) formatting: an unambiguous implementation of Markdown for scholarly writing.
  
  Google doc - https://docs.google.com/document/d/1nBjBgxzuHPoCEWvFeNXZjt33xfx4BRyIedslOxiQZa0/edit

  Can be rendered to other formats as using [Pandoc](http://johnmacfarlane.net/pandoc/). To render to PDF with a table of contents use the following:
  
  cd /home/arb/ownCloud/Nottingham/OSMGB/Git/OSMGB/Documents/2015_ServiceResurrection

  pandoc -f markdown -t latex -N -V geometry:margin=1in  2015_06_08_UoN_OSMGB_Hardware.md --filter pandoc-citeproc --latex-engine=xelatex --toc -o 2015_06_08_UoN_OSMGB_Hardware.pdf


  \newpage
---

\newpage

# OSMGB hardware meeting 20150608

time: 11am-12am

Location: Lenton Hurst

in attendance:

* Anthony Beck (ARB), 
* Craig Place (CP), 
* Shaun Hindley (SH)


## Summary

On 20150608 a short meeting was held between Anthony Beck, Craig Place and Shaun Hindley to discuss the decommissioning of the *at risk* OSMGB *server 1* running Windows 2003 server. Thanks to Craig and Shaun for attending and making this an easy meeting :-)

The **short term solution** is to mitigate the risk of *server 1*. This will entail:

1. The creation of a basic *windows server 2008* virtual machine (VM)
1. Installation of the required software
	* Oracle
	* 1Integrate
1. Migration of rules, settings etc. from *server 1* to the new VM
	* Testing of the environment
1. The creation of a minimalist backup of *server 1* as a VM
1. The decommissioning of *server 1*

Ideally all phases can be completed prior to the July risk date (the critical tasks are 2 and 3). However, if these do not occur then server settings can always be accessed from the VM created in points 4 and 5.

Whilst this may not create the long term instance it creates a working instance. In September 2015 a new virtual server farm will be available at UoN. At this point this base installation can be extended and new virtual disks added and/or the c: drive extended. These disks will be needed to provide enough space for the Oracle database and the 1Integrate cache.

Critical to the creation of the VM in 4 and 5 is an understanding of the required disk space. *Server 1* contains three drives (C, D and E) that contain 650gb of data (50, 450 and 150 respectively). The assumption is that D and E contain data and C contains software and settings. This assumption needs verifying (for example D contains the Radius Studio install and required batch files).

The **longer term solution** is predicated on the new server farm being in place in September 2015. At this point the replacement *server 1* VM will be reconfigured, *server 3* will be packaged as a VM and *server 2* will be re-built from scratch (without the at-risk components). At this stage funds need to be in place. However, the required funding structure has yet to be established.

## Action points

* CP/SH
	* Spin up basic VM to replace *Server 1* (the at risk *windows 2003* server)
* ARB and SH
	* Both look into Oracle licencing at UoN
* ARB
	* Arrange licence for 1Integrate
* ARB and/or Amir Pourabdollah (AP) (with 1Spatial support)
	* Confirm D and E drives are data only drives
	* Install Oracle and 1Integrate on new VM
	* Migrate settings from *Server 1*
	* Test environment on data subset 
* CP/SH
	* Package a VM of *Server 1* (only include the C drive (subject to action point above))
		* Check the VM is valid
	* Decommission *Server 1*
	* Advise on funding structure for the server farm
* All (come September and the new server farm)
	* Migrate other machines over
