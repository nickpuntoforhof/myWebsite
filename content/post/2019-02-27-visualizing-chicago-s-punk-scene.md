---
title: Visualizing Chicago's Punk Scene
author: Noah Stafford
date: '2019-02-27'
slug: visualizing-chicago-s-punk-scene
categories:
  - Music
tags:
  - shiny
---
<img src = "/img/chicagopunkshinyscreencap.png" alt="Chicago Punk Shiny Screencap"/>

[https://jammypacstrap.shinyapps.io/chicagoBandNetwork/](https://jammypacstrap.shinyapps.io/chicagoBandNetwork/)

<iframe id="chicagoBandNetwork" src="https://jammypacstrap.shinyapps.io/chicagoBandNetwork/" style="border: none; width: 100%; height: 850px" frameborder="0"></iframe>

Here's something I coded up in an effort to teach myself R Shiny, a package that allows coders familiar with R to write interactive web apps in R.  It's a visualization of the 80's Chicago Punk Scene.  The data is based on a page found in the WNUR Rock Show Bible, a binder packed full of hand-made info sheets on historical rock scenes that resides in the exec room of Northwestern University's radio station.  I then supplemented this information with information found at the [Chicago Punk Database.](http://punkdatabase.com/wiki/Main_Page)

The main idea was to visualize the complex web of relationships that is created as a scene develops and people join bands, leave to join other bands, break off with half of their old band and form a new band, change the name of their band, go solo and get those guys from that other band to join their band, form a super-group with a rotating roster of musicians from the scene, and on and on.  I thought a network would be a great way to visualize this, consisting of bands as the dots or "nodes" and shared members between bands as the lines or "edges" between the nodes.

R Shiny allowed me to take this initial idea and expand on it.  The visualization as it stands now allows the user to click a band, which then initiates the display of a short blurb about the band, information about which bands shared members with the selected band and the names of those members.  If the user is interested in learning more about the selected band, they are then able to click links to discogs, rateyourmusic and allmusic, which opens up a new tab and queries these sites for the selected band name.

This method of visualizing bands is primarily limited by the lack of available structured data.  All the data I used I had to enter myself.  Band member data is displayed on numerous websites such as discogs, rateyourmusic, and allmusic but none of this data is easily accessible.  The next step for this project would be to figure out how to use the discogs api to scrape the data I need.

Also, I don't know who this Pierre Kezdy fellow is, but he seems to have played bass in literally every single band that existed in Chicago from the early 80's to the mid-90's.  This guy really threatened to turn the whole network into an enormous visual mess, which challenged my thinking about a network being an effective way to visualize music scenes.  If you're looking to connect every band with every other band that shared any members, the problem is that the amount of edges you need to connect all the nodes is going to increase quickly.  If three bands share a member, that's three edges to connect them.  If six bands share a member, that's 15 edges to connect six nodes.  I decided to avoid this issue by being judicious with assigning edges in Pierre's case, mainly by creating edges that had direct chronological merit.  For instance, Kezdy went from playing bass in Strike Under to playing bass in Trial by Fire to playing bass in Naked Raygun to playing bass in Arsenal.  Do I need to specify an edge between Strike Under to Arsenal?  It seems redundant, and will only gum everything up visually.  So I tried to limit creating edges only for direct, chronological member movement between bands.  If I were to automate the data collection process, I would also have to figure out how to deal with this issue on a larger scale.

So let me know if you have any suggestions -- on what I can improve visually, on any features you think would be cool to integrate, or if you know a bunch about the Chicago punk scene and want to tell me about all the seminal bands I've ignorantly omitted, fire away in the comments box.