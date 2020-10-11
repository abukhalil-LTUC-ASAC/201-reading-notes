# API's The Application Programming Interface

You might have recalled an app I did, using [google map's API](https://github.com/AbuKhalil95/RE_projects). I had no clue how it worked by then, I did know google, and how to cram code and debug, and a month later I was able to communicate with google directly, ask them for their neat software google maps after providing my credit card data, cram my own data into it and present it in a neat way.

It is essentially what API is about, its a way to borrow a software and its usefulness without directly owning it. Managing your requests and gets and what not to solve problems without coding everything from scratch is the skillset needed to get through this.

You might have recalled [what google found out about making the perfect team, millions of dollars later](https://www.google.com/amp/mobile.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.amp.html). Same could have been said about API's and HTTP, a [wonderful gist](https://gist.github.com/brookr/5977550) by a fellow githuber from codefellows explained it in a detail that is meaningful to both technical and non technical people! The skim brought me to attention that most people in software development don't really think much about how the machines communicate between each other, if only more resources were poured into that we could have already a true ***HIVEMIND*** of simultaneous and real time communication between all machines, at 0 MS ping! Imagine all of these gaming sessions wasted to lost packets.

A working API with Node.js would be [SuperAgent](https://visionmedia.github.io/superagent/), its a *"light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs. It also works with Node.js!"*.

To get started, the following API's have been acquired: 

- [LocationIQ](https://my.locationiq.com/dashboard/?firstLogin=1)
- [Weather Bit API Docs](https://www.weatherbit.io/)
- [Yelp API](https://www.yelp.com/developers/documentation/v3/business_search)
- [The Movie DB API Docs](https://developers.themoviedb.org/3/getting-started/introduction)
- [The Hiking Project API](https://www.hikingproject.com/data)

## Working with SuperAgent
Starting off with: 

```
 request
   .post('/api/pet')
   .send({ name: 'Manny', species: 'cat' })
   .set('X-API-Key', 'foobar')
   .set('Accept', 'application/json')
   .then(res => {
      alert('yay got ' + JSON.stringify(res.body));
   });
```

It is apparent how simple the layout looks. The rest could take you into a deep dive into the [*documentation*](https://visionmedia.github.io/superagent/).
