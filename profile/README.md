## Hi there 👋

I've got distributed, disconnected systems to help me do things like publish a podcast (`bootiful-podcast`), compose weekly roundups (`this-week-in`), and - soon - to enrich videos on youtube (`youtube-atoms`). 

Could this be a chance to consolidate? Force as much as possible into one modular monolithic codebase using Spring Moduliths and GraalVM? 

## considerations

this api backend would expose feeds, eg, ATOM for content published (blogs, youtube videos, podcasts), as well as a read-only graphql api. so i could then build bootifulpodcast.fm, joshlong.com, springtipslive.io, etc., to talk to these feeds. 


## features 

starting in 2025, i'm going to try to track things - ["features"](https://github.com/bootiful-media-mogul/features) - that span both the backend and the frontend in the central `features` repositories, so i've created a central `features` repository. start large feature implementation tickets in there and link to sub-issues in the constituent repositories. 

ideally, we'd converge on consistent labels there, too.




