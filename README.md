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

## Common Standards
* [data-conversion-api] (https://github.com/online-bridge-hackathon/data-conversion-api) - An API for converting different file formats (pbn, lin) to JSON
* [data-formats] (https://github.com/online-bridge-hackathon/data-formats) - Specifications and Example JSONs

## Roadmap
![Bridge Hackathon Roadmap](https://github.com/online-bridge-hackathon/bridge-hackathon/blob/master/Bridge%20Hackathon%20Roadmap.png)

### A platform where...

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

#### ...bridge organisers, particularly clubs (local, regional, national, international)
- can organiser their online bridge clubs
- can hold one-off matches
- can set up and manage club chat groups for players and organisers that persists across logins

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


## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
