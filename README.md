# Transportation Networks 

Transportation Networks is a networks repository for transportation research.  
If you are developing algorithms in this field, you probably asked yourself 
more than once: where can I get good data?  The purpose of this site is to 
provide an answer for this question! This site currently contains several examples 
for the traffic assignment problem.  Suggestions and additional data are always welcome.

This repository is an update to Dr. Hillel Bar-Gera's [TNTP](http://www.bgu.ac.il/~bargera/tntp).

# Current Network Test Problems

  1. Anaheim
  1. Austin
  1. Barcelon
  1. Berlin-Center
  1. Berlin-Friedrichshain
  1. Berlin-Mitte-Center
  1. Berlin-Mitte-Prenzlauerberg-Friedrichshain-Center
  1. Berlin-Prenzlauerberg-Center
  1. Berlin-Tiergarten
  1. Birmingham-England
  1. Braess-Example
  1. chicago-regional
  1. Chicago-Sketch
  1. GoldCoast
  1. Hessen-Asymmetric
  1. Philadelphia
  1. SiouxFalls
  1. Sydney
  1. Terrassa-Asymmetric
  1. Winnipeg
  1. Winnipeg-Asymmetric

# How To Download and Add Networks  

Each individual network and related files is stored in a separate folder. There
are a number of ways to download the networks and related files:
  - Click on a file, click view as Raw, and then save the file
  - Clone the repository to your computer using the repository's clone URL. This is done with a Git 
      tool such as [TortoiseGit](https://tortoisegit.org).  Cloning will download the
      entire repository to your computer.

To add a network, create an issue, which will notify the TransportationNetworks team.  We will then 
reply to coordinate adding the network to the site.  Make sure to create a README in 
[Markdown](https://guides.github.com/features/mastering-markdown/) for your 
network test problem as well.  If you are interested in contributing in a more 
significant role, please get in touch with some of the team members.  Thanks!
  
# License 

All data is currented donated.  Data sets are for academic research purposes only.  Users are
users are fully responsible for any results or conclusions obtained by using these data sets.
Users must indicate the source of any dataset they are using in any publication that relies 
on any of the datasets provided in this web site.  The TransportationNetworks team is not 
responsible for the content of the data sets. Agencies, organizations, institutions and 
individuals acknowledged in this web site for their contribution to the datasets are not 
responsible for the content or the correctness of the datasets.

# The Traffic Assignment Problem

The Traffic Assignment Problem is one of the most basic problems in transportation research. 
Theoretical background can be found in “The Traffic Assignment Problem – Models and Methods” 
by Michael Patriksson, VSP 1994, as well as in many other references.

# TNTP Data format 
Many of the datasets on TransportationNetworks are in TNTP format.  TNTP is tab delimited text files, 
with each row terminated by a semicolon.  The files have the following format:
 - First lines are metadata; each item has a description.  An important one is the `<FIRST THRU NODE>`. 
   In the some networks (like Sioux-Falls) it is equal to 1, indicating 
   that traffic can move through all nodes, including zones. In other networks when traffic is not 
   allow to go through zones, the zones are numbered 1 to n and the `<FIRST THRU NODE>` is set to n+1.
 - Comment lines start with ‘~’.
 - Network files – one line per link; links are directional, going from “init node” to “term node”.
     - Link travel time = free flow time * ( 1 + B * (flow/capacity)^Power ).
     - Link generalized cost = Link travel time + toll_factor * toll + distance_factor * distance
     - The network files also contain a "speed" value for each link. In some cases the "speed" values 
     are consistent with the free flow times, in other cases they represent posted speed limits, and 
     in some cases there is no clear knowledge about their meaning. All of the results reported below 
     are based only on free flow travel times as described by the functions above, and do not use the speed values.
     - The standard order of the fields in the network files is:
       - Init node
       - Term node
       - Capacity
       - Length
       - Free Flow Time
       - B
       - Power
       - Speed limit
       - Toll
       - Link Type
 - Trip tables – An Origin label and then Origin node number, followed by Destination node numders and OD flow 

```
Origin origin#
destination# , OD flow ; …..
```

# Other Related Projects 

 - [Frank-Wolfe algorithm](http://www.bgu.ac.il/~bargera/tntp/FW.zip) that demonstrates how to read these 
   data formats and runs a FW assignment.  The header file "stdafx.h" is for Microsoft Visual C (MSVC) compiler. On 
   Unix and other compilers it can be simply omitted.
 - [Origin-Based Assignment (OBA) algorithm](http://www.openchannelsoftware.org/projects/Origin-Based_Assignment/)
 - [NeXTA](https://code.google.com/archive/p/nexta/) Open-source GUI for visualizing static/dynamic traffic assignment results
 - [seSue](http://people.sutd.edu.sg/~ugur_arikan/seSue/) is an open source tool to aid research on static path-based 
   Stochastic User Equilibrium (SUE) models. It is designed to carry out experiments to analyze the effects of 
   (1) different path-based SUE models associated with different underlying discrete choice models 
   (as well as hybrid models), and (2) different route choice set generation algorithms on the route choice 
   probabilities and equilibrium link flows. For additional information, contact [Ugur Arikan] (ugur_arikan@sutd.edu.sg)

# History

 - Explanation about `<FIRST THRU NODE>`, May 17, 2007.
 - Add Berlin area networks, May 17, 2007.
 - Add reference to third version of Sioux-Falls (Suwansirikul), May 17, 2007.
 - Comments on the FW code, May 17, 2007.
 - Add map for Anaheim, April 12, 2007.
 - Change Philadelphia network file to standard format, April, 12 2007.
 - Change file names to uniform convention with *.txt, April 12, 2007.
 - Change the toll factors in the Chicago networks, August 27, 2007. (The new toll factors are the ones originally used in my own papers. For a certain period the toll factors indicated here were zero, so it there may be publications reporting results with zero toll factors.)
 - Add optimal OF values for different networks, August 27, 2007.
 - Add link lengths from Morlok’s report to the Sioux Falls network. November 19, 2007.
 - Update Berlin area networks data, and added converted version for TNTP format. January 15, 2008.
 - Austin data added. January 12, 2011.
 - Added explanation of the units of OD flows for Sioux Falls. March 31, 2011.
 - Addition on duplicate links as pointed out by Hong Zheng, December 3, 2012.
 - Correction of the description of the Winnipeg network from "154 zones; 1067 nodes; 2975 links" to "147 zones; 1052 nodes; 2836 links", pointed out by Huayu (Cathy) Xu, February 7, 2013.
 - Addition of explanation about node coordinates, and references, for the Chicago Sketch network. April 14, 2013.
 - Addition of the modified PRISM network. May 5, 2013.
 - Addition of three asymmetric networks provided by Esteve Codina Sancho, August 4, 2013.
 - Add discussion on network design variants of Sioux Falls, August 30, 2013.
 - Add the "Enriched Sioux Falls Scenario with Dynamic and Disaggregate Demand" developed by Artem Chakirov, March 5, 2014.
 - Add Sydney and Gold Coast networks. April 24, 2014.
 - Add links to Chicago Regional PAS maps. December 22, 2014.
 - Add dynamic version of Sioux Falls by Michal Nitzani, June 22, 2015.
 - Updated version of the Gold Coast network (original format), provided by Mark Raadsen (the previous file had corrupted node coordinates), August 25, 2015.
 - Link to seSue added, January 1, 2016.
 - Revise Goldcoast network, February 2, 2016.
 - March 2016 migration to GitHub
 
