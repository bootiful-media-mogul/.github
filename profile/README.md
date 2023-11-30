## Hi there 👋

I've got distributed, disconnected systems to help me do things like publish a podcast (`bootiful-podcast`), compose weekly roundups (`this-week-in`), and - soon - to enrich videos on youtube (`youtube-atoms`). 

Could this be a chance to consolidate? Force as much as possible into one modular monolithic codebase using Spring Moduliths and GraalVM? 

## considerations 

I would redo the UIs for all of the experiences, ideally just deploying the dumbest ugliest HTML pages you've ever seen and throwing away the tens of thousands of lines of Typescript and CSS code in all the other `studio.*` experiences.

I would still keep the auth server and gateway setup. one wonders: could i use spring cloud gateway for mvc? but now i'd just have one of each. No more duplicative gateways.

I'd standardize on AOT+GraalVM, Spring Boot 3.2, Java 21, RabbitMQ, Spring AI, JobRunr, MVC, GraphQL, Maven, Postgres, Spring Data JDBC, Docker Compose, Direnv, and my various libraries. (Maybe i could pull all of them into a `joshlong-bom`)?

There are still a few different Python workloads (the whisper transcription service, and the audio mutliplexer for the podcasts) that will need to run separately cordoned off via RabbitMQ. 

I could create and leverage standard services across the entire suite: AI audio to text, image generation, chat services, social media notifications, s3 storage, scheduled jobs, etc.

I would design the whole thing to have multitenancy, so that a user can login, and (a) publish blog posts (to _their_ feed), (b) create a podcast and publish episodes for it (c) link a youtube channel and give people a way to, given a published youtube video, have the youtube-atoms suite at their fingertips.

A user would also be able to register tags and feed sources that should be monitored then have those items presented to them. if they like, they can select a range of them and have them turned into a new blog post, which - witha touch of a button - they could have ChatGPT spruce up. 

A user could specify a publication target for each of their blogs and when they hit _Publish_ automatically have the blog published to that target: Contentful, a Github pages repository, etc.

We'd deploy the API and then for the studio experience we'd have a new , cleaner, monolithic vue.js app for all the pages (youtube, feeds, blogs, podcasts, etc.). there would also need to be an ADMIN functinoality somehwere. maybe per page? that way the user can link podcasts, youtube channels, podbean accounts, configure tokens, contentful tokens, github blogs, etc. 

multitenancy would center around oauth. maybe i use google oauth or sprign authorization server. probably easier to start with google. fewer moving parts. we could register new users dynamically this way. sign in with and u get a new account and multitenancy around thrat account. not sure how a user using oauth and google would then change their email address later on , though. 







<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
