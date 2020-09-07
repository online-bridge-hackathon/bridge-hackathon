<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-0-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

# bridge-hackathon

[![Join the chat at https://gitter.im/bridge-hackathon/community](https://badges.gitter.im/bridge-hackathon/community.svg)](https://gitter.im/bridge-hackathon/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Bridge Hackathon is a real, currently online-only hackathon, started on 23 May 2020. The hackathon participants created a modular suite of cloud-native services (projects) to build multiple, modern end user applications, such as a Bridge game server (improving on the work of BBO, OK Bridge, BCL, FunBridge, etc).

## Projects
1. [DDS](https://github.com/online-bridge-hackathon/DDS) - An api that returns DDS results for a given deal or partial deal
2. [Deal](https://github.com/online-bridge-hackathon/Deal) - A web service that accepts request by APIs and returns 1+ bridge deals
3. [OCR](https://github.com/online-bridge-hackathon/OCR) - Optical Character Recognition API that converts deal images to text format
4. [Data Converter](https://github.com/online-bridge-hackathon/Data-Converter) - Converts bridge deal data formats between JSON, PBN, etc
5. [Tournament] - Organises users, tables, deals, scores  (not yet created; name may change)
6. [Scores] - Accepts contract results and returns scores  (not yet created; name may change)
7. [Storage] - Storage for played deals (not yet created; name may change)
8. [Platform] - Play server where users can play bridge  (not yet created; name may change)
9. [Robots] - A place our Robots will be developed and hang out! 

### Try out our services!
Listed are current services on our Production clusters.

#### Deal (Prod)
Returns [UUID](http://www.rpbridge.net/7z68.htm)-encoded random deals as a JSON object
```
curl https://deal.prod.globalbridge.app/api/deal
```

##### Converter (Prod)
Accepts a PBN file (replace path with your own) and returns the conversion as a JSON object
```
curl -F "file=@/tmp/test.pbn" https://converter.prod.globalbridge.app/api/boards/test
```

#### DDS (Prod)
Accepts a full hand encoded as a JSON object and returns the DDS result as a JSON object
```
curl --header "Content-Type: application/json" --request POST --data '{"hands":{"S":["D3", "C6", "DT", "D8", "DJ", "D6", "CA", "C3", "S2", "C2", "C4", "S9", "S7"],"W":["DA", "S4", "HT", "C5", "D4", "D7", "S6", "S3", "DK", "CT", "D2", "SK","H8"],"N":["C7", "H6", "H7", "H9", "CJ", "SA", "S8", "SQ", "D5", "S5", "HK", "C8", "HA"],"E":["H2", "H5", "CQ", "D9", "H4", "ST", "HQ", "SJ", "HJ", "DQ", "H3", "C9", "CK"]}}' https://dds.prod.globalbridge.app/api/dds-table/
```



## Common Standards
* [data-conversion-api] (https://github.com/online-bridge-hackathon/data-conversion-api) - An API for converting different file formats (pbn, lin) to JSON
* [data-formats] (https://github.com/online-bridge-hackathon/data-formats) - Specifications and Example JSONs

## Roadmap
<img src="https://github.com/online-bridge-hackathon/bridge-hackathon/blob/master/images/Bridge%20Hackathon%20Roadmap.png" title="Bridge Hackathon Roadmap" height="70%" width="70%">


### These are some of the services we plan to deliver:

#### A fully-featured, modern online bridge platform

Play with and against others in a wide variety of formats at no charge.

We also plan to provide this service to bridge organizations, companies, and researchers where they can market it under their own names, free for moderate usage and with micro-payments for high usage.

#### A double-dummy solver

Enter a deal onto a web page and see the number of tricks declarer can take from each position with each trump suit, with best play and defense. Step through the play trick by trick to see how.

#### A deal formatter

Enter an auction and a deal on a web page and have it rendered for you in a variety of formats, suitable for emailing (text), posting on a website (HTML), or typesetting (Postscript or PDF.)

#### A deal generator

Request a number of deals, randomly dealt or to your specifications, for use in a tournament or bidding practice.

#### An optical card recognizer

Take a photo of a deal after it's been played and use the results to generate hand records, save in a database, or format with the deal formatter above.

Set up a table video camera to record all bids and play, for live VuGraph, recorded viewing. TDs can use it to monitor matches and avoid problems while researchers can use it for analysis.

#### A universal bridge results database

This would be a superset of the existing isolated repositories, bringing all our bridge data together for better user experiences, such as player development and research. Retrieve any deal that's been played online or face to face, limited only by the data that's been added to the system. Look for your favorite stars or partners, or your own triumphs and tragedies. Compare your results to others. Look for which styles and conventions are most effective and why. Capture trends over time.

### This is a list of our intended features where...

##### ...bridge players 
- can play an informal match with friends
- can play a match with their bridge club
- can invite a partner (or robot) to join in any match by URL (link)
- can watch one or more live or recorded matches in a multi-pane viewer, e.g. both tables at a teams match
- can play in more than one match at the same time (obviously with limitations: e.g. not in the same tournament)
- can join a variety of groups (table, tournament, friends)
- can set up their own group (create once - each group persists across logins)
- can invite friends to join their group
- can chat via text and emojii with any group
- can chat via video with their table group
- can import or link groups of friends from other chat platforms (WhatsApp, Hangouts, WeChat, Messenger) 
- can join an interactive bridge class with a teacher
- can find pro players and teachers easily and eaily message them and/or book a session

#### ...Bridge clubs (local, regional, national, international) and organisers
- can organiser their online bridge clubs
- can hold one-off matches
- can set up and manage club chat groups for players and organisers that persists across logins
- can organise player payments completely independently from the platform
- can enable tournament sign up pages (updated when played) and download player lists for club accounting reasons
- can hire the "venue" according to our freemium model (free or micro-payments)
  _This a low-profit platform with cloud infrastructure costs - all contributors and leads are volunteers)_

#### ...Tournament Directors (TD)
[ref: TD Feature Requests](https://docs.google.com/document/d/1JAYtRJsGcjBOtSQjE7F4FGEm0vxa3Byd8o7eA9-5zBU/edit)
- can use a dashboard of scores and progress (inc pace) of tables in play
- can run events with seeding, stratification & handicapping
- can determine start lineups (re: seeding)
- can run multi-session events with carry-forwards
- can run Pairs tournaments with Swiss, Mitchell (two-winner), Howell (one-winner) movements
- can select Pairs scoring method: Cross IMPS, VPs, Butler (when IMP-scored), Handicaps/stratified events
- can get “pair datum” results and ranking using desired scoring method (Butler, cross IMPs)
- can run Teams tournaments with Swiss, Multiple Teams (4 or 8), Knockouts, Leagues
- can select Teams scoring method: IMPS, Aggregate, Continuous VPs, Discrete VPs, Point-a-Board, Hybrid
- can select non-Neuberg factoring on boards with artificial scores
- can enable Teams to change lineups during a session
- are not limited by enforced sections (there will be none by default, but can be created if needed)
- have the ability to set a change of opponents at half time
- can set live feed and results display to be delayed until all tables have finished a board
- can cut the movement short, if needed (e.g. juniors, novices)
- can set up Tournament chat groups that can be open and closed at any time chosen
- can record and replay chat/video messages to any group they are a member of (table, tournament)
- ability to award procedural penalties
- ability to add a pair of robots if there is a half table
- can receive specific alerts from players/kibs at tables (e.g. slow play, bad behaviour)
- get quick access to a full log of table actions (bid, play, alerts, table talk)
- can set adjustable "kick" period where slow players are auto-kicked - if that feature is required
- can award weighted scores, split scores and make Neuberg adjustments for boards that include artificial scores
- can define the score correction window
- can output results in various formats: USEBIO, Text, HTML, CSV, JSON


#### ...Bridge Teachers
[ref: Teacher Feature Requests](https://docs.google.com/document/d/1tQTpZuHvaFlMZuE2xDgs675IekY7iwEfoomUzxmjXlk/edit)
- can schedule or create ad-hoc classes of multiple tables
- can set up a class (group)
- can invite learners to join a class by URL (link)
- can assign learners to a table or allow them to choose their own
- can generate specific sets of deals and store them on the platform for retrieval any time
- can easily choose deals (random or specific) for each or all the tables
- can with "one click" do multiple saved actions: send learners to assigned seats, deals a prepared hand to bid and play, returns to the class/theatre at the end
- can chat via text and emojii with any group (class, table)
- can chat via video with any group (class, table)
- can display hands dynamically in the group (class, table)
- can display uploaded notes in the group (class, table)
- can manipulate the deal mid-lesson ("If we put the ⧫K in this hand, let’s see what happens…")
- can cut the movement short, if needed (e.g. juniors, novices)

#### ...Software Developers (backend, frontend, UI/UX, DevOps, systems architects, standards)
- can contribute to our globally available, open source code, docs, designs (MIT license)
- can use our globally available, open source code, docs, designs (MIT license)
- can build new projects within the Bridge Hackathon framework and garner support and resources
- can join the leadership of Bridge Hackathon (with contributions, skills, commitment)

#### ...3rd party businesses (NBOs, existing Bridge platforms, entrepreneurs, app developers, ...)
- can do everything in the Bridge clubs list
- can do everything in the Software Developers list
- can access and use the dedicated, independent Bridge component services (Deal, DDS, Converter, OCR, etc) with our API freemium model (free or micro-payments)


## Contributors ✨

Developer documentation is available at [README-developers.md](README-developers.md)

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
