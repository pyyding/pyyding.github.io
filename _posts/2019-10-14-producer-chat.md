---
layout: post
title: 'Product Experiment: #1 Producer Chat'
published: true
---

[![Producer Chat]({{site.baseurl}}/2019-10-14-producer-chat/images/producer-chat-cover.png)](https://www.youtube.com/watch?v=t0i3M46cG8s)
```
tl;dr

Idea: 
WIP Chat / Makerlog knockoff for indie music producers

-------------

Product
Web app
- front-end: Vue with Vuetify framework
- back-end: Google Firebase with Firestore

Slack bot 
- serverless with Firebase Functions

-------------

Outcome:
- a few hundred e-mails from various producers
- considerable amount of knowledge regarding building communities
- first PH launch
```

### Intro

Hey guys, last year I completed an adventure with my first side project called Producer Chat. I have wanted to sum things up for a while but never had a blog where to yabber about this until now. 

First things first: what put the side project ball rolling was that I applied for a product engineer job position without really knowing what was that about. I knew the core concept but never actually knew the processes etc. During the interview I was asked if I had even read the three absolutelly essential books and I was like, "nah, never heard of them", so he straight up stopped me there.

Here's the email I got

> Hi Kaspar,
>
>
> Very good speaking with you at this time and as mentioned, while I can't proceed to the next stage at this point, kindly know that this is because we dont have the resources to onboard you in a proper way at this time and also due to limited product knowledge.
>
> Worry not as you can address this with some degree of self study.
>
> As mandatory reading I recommend you checking out :
> http://theleanstartup.com/ - The Lean Startup by Eric Reis
> http://zerotoonebook.com/ - Zero to One by Peter Thiel
> https://startupclass.samaltman.com/ - How to start a startup by Sam Altman.
>
> Once you have had the chance to go over these please do drop me a line.

I read the books in a couple of months but never wrote them back. Instead I was accepted for another position and have enjoyed it so far. Enough intro, cut to the chase, Kaspar!

### Prequel

About this time, a year ago I was just introduced to indie maker communities by Alex, the founder of [Unicorn Platform](https://unicornplatform.com). We had met in a coworking space in Bangkok and he just kept pinging me "Kaspar, what's stopping you to build something?". Studying music producing, I came up with an idea to steal _(phrasing intentional 😄)_ the "chat group, todo list, FAQ" concept that's super popular amongst makers ([MakerLog](https://getmakerlog.com), [WIP Chat](https://wip.chat/)) and port it for beat makers and indie producers. 

Honestly, I knew fairly little about music production so I decided to pitch the idea to Laze, this instructor guy from an Udemy course I had just taken. He ended up loving it and shortly after we started building it.
![laze-udemy.png]({{site.baseurl}}/images/2019-10-14-producer-chat/laze-udemy.png)

### Building The MVP

We worked on Producer Chat for a couple of months, ended up with a Slack chat group and a web app. Both were integrated together with a nifty little Slack bot named Dilla Bot _(after J Dilla, an infamous beat producer)_. Dilla bot allowed you to add todos, post tracks for feedback, and provided a few other shortcuts directly from chat.
![producer-chat-screenshot.png]({{site.baseurl}}/images/2019-10-14-producer-chat/producer-chat-screenshot.png)

### The Launch

After Product Hunt launch, we received solid feedback from the maker community and things started to feel real. We boarded a few producers a day ⁠— Producer Chat was growing. We were even approached by an investor who I ended up having a Whatsapp call with. Allegedly the investor guy was casually cruising his yacht near Maldives at the time of the call. Just a fun sidenote that PH can connect you to all kinds of interesting people.

We had set up an IG account, followed-unfollowed, DM'd bedroom producers, posted a bunch of stuff for a few weeks but the interest for the product was super low and it took a lot of time. After a while the organic growth stopped as well ⁠— we had shut it down. As an upside we got a few hundred emails which we can potentially use for other music production related endeavours.

## Takeaways

**Creating a community should start with a super specific goal** 
Even our domain was as general as it could have been (`producer.chat`). The members were doing different music, there was very little interactions. It resulted the community not to bond and fade away quickly. I could imagine something like this to work for just a specific genre of music but definitely not "all music".

**Picking the right platform for the chat**
For some reason a lot of music producers are gamers and pretty much all gamers use Discord for chat purposes. This brings up a question why did we even go for Slack. We thought we could avoid  the "gamer kids" and bring on more serious musicians. It was one of the worst decisions we made. More serious producers aren't even online. The "gamer kids" are spending so much time behind the computer and many are already sooo popular in SoundCloud space, it's crazy.

**Google Firebase is (was?) not testable**
To keep things simple, I used Firebase as a back-end. 90% of this was a bliss but the 10% absolute misery. Naturally, I wanted to cover important parts with tests but it was literally impossible. Google did not even have necessary tooling for that at the time. All the research resulted me getting an invitation to a Google Alpha program for a something Google was building in order to fill that gap. Meaning, things might be a lot better now.

**Building a side project with two people**
It is risky, that's for sure. You feel like you always have to align with other's thoughts. Then there is the workload balancing because you want to make sure both would get to contribute similarly. Then you or them might miss a deadline from time and it will cause minor headics. All these things will cost you time and a side project should not be frustrating to do. 

After a whilel, we ended up building in a way that I was shipping features and Laze was mainly helping me with planning the next steps and giving feedback. There were loads of other things like keeping the community alive and organising marketing stuff but essentially he took the role of an advisor. This is the form of co-building, I would totally recommend. Be the main guy, take extreme ownership over your actions but also have an expert in hand you can regularly discuss things with.

**Indie Producers ARE Indie Makers**
Music is a different kind of world but all the hustle is the same for both groups. Ship songs, put stuff in front of people, see what works, improve, repeat the process. Analogically goes for makers and products.

## Conclusion

Producer chat did not blow viral but similar products have emerged (f.e [Metapop](https://metapop.com/)). Making me think we were at least heading towards the right direction. By studying the space I'm already building a new music related product in my head and it definitely will be better than Producer Chat. Thanks for reading, let me know if it triggered any thoughts or questions.
