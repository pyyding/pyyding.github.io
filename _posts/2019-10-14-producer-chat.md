---
layout: post
title: 'Product Experiment: #1 Producer Chat'
published: true
---
```
tl;dr

Idea: 
Chat + todo list community for music producers

Product:
Web app (https://producer.chat)
front-end: Vue with Vuetify framework
back-end: Google Firebase with Firestore
Slack bot: Firebase Functions

Results:
Few hundred e-mails from various producers
```


### Prequel

About this time, a year ago I had just found indie maker communities on the web. Studying music producing, I came up with an idea to steal the "chat group + todo list" concept ([MakerLog](https://getmakerlog.com), [WIP Chat](https://wip.chat/))
and port it for beat makers, indie producers. 

Honestly, I knew fairly little about music production so I decided to pitch it to this instructor guy from an Udemy course I had taken earlier.
![laze-udemy.png]({{site.url}}/images/2019-10-14-producer-chat/laze-udemy.png)

### Building The MVP

We worked on Producer Chat for a couple of months, ended up with a Slack chat group and a web app. To integrate both together I created a small Slack bot. It allowed you to add todos, post tracks for feedback directly from the chat. 
![producer-chat-screenshot.png]({{site.baseurl}}/images/producer-chat-screenshot.png)

### Post Launch

After Product Hunt launch, we received quite good feedback and things started to feel real. We boarded a few producers a day and things were going uphill. We were even approached by an investor who I ended up having a Whatsapp call with.

We set up an IG account, followed-unfollowed, DM'd bedroom producers, posted a bunch of stuff for a while but the interest for the product was super low. After a while the organic growth stopped as well and we had shut it down. As an upside we now have a few hundred emails that we could potentially use if needed.

## Takeaways

**Creating a community should start with a super specific goal** 
Even our domain was general(`producer.chat`) and everyone were doing different music. It resulted the community not bond and fade away from the chat. I could imagine something like this to work for just a specific genre of music. We marketed it out as something for "bedroom producers" but it only got us greener musicians 😄.
 
**Google Firebase is not testable (maybe it is now)**
Naturally, I wanted to cover important parts with tests but it was literally impossible because of missing tooling by Google. All the research resulted me getting an invitation to Google Alpha program for a tool that was supposed to fill that gap. So things might be different now.



