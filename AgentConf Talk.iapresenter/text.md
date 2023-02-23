### Database technologies for offline-first apps

So I have to admit that I didn’t put much thought into the title.

Here’s a new title.

---

## Preparing your app for Mars

So let's learn how to prepare your app to work on Mars.

---

/assets/maxresdefault-1.jpg
background: true

I like the idea of Matt Damon downloading my app on a USB stick, and taking it along on the long trip.

---

Offline retreat is my invention, and it's an idea of going on a weekend trip with a laptop, but without internet access.

Because computers are fun, but internet is addictive.

You can still write code, or write articles or book outlines. Or design your home in 3D, or learn how to use Vim properly.

Computers don't make your brain go mushy. It's your internet.

	 🪐 Space travel
	 ✈️ Planes & trains
	 ⛵ Boats
	 🪖 War zones
	 🫶 Developing countries
	 ⛰️ "Offline retreat"



---

### About me

Quick introduction

---


	**Vojtech Rinik**
	* co-founder @ **[reflect.app](https://reflect.app)**

I'm a co-founder at Reflect, and it's coming up on 2 years now.

---


/assets/CleanShot 2023-02-17 at 13.51.30@2x.png
size: contain

Reflect is a E2E encrypted note-taking app for taking networked notes in the style of Roam/Obsidian.

It’s a great match for the offline-first approach.

---

Before, I've had a typical web developer carreer. Maybe with the exception of dabbing into whole Apple ecosystem.

	**Vojtech Rinik**
	* 
	* 2009 Ruby on Rails
	* 2012 JavaScript SPAs
	* 2017  iOS/Mac (ObjC, Swift)
	* 2019 React, TypeScript
	* 2021 **[reflect.app](https://reflect.app)**


---

###  Native apps

In the world of native apps it’s quite normal to build something as polished as Things:

---


/assets/Group.png
size: contain

---

#### Is there an Electron app with that level of polish?


---


/assets/CleanShot 2023-02-18 at 08.36.35@2x.png
size: contain

It was called Quill, it was a Slack competitor, but it was acquired by Twitter, so it’s dead to me now.

---

Look at that design. Even the icon looks like it came from Jony Ive's dream.

* Transparent sidebar - Linear uses the same trick
* Native-like UI elements
* Perfect match with the colors
* Animations are just right - not too many, not too few
* Uses sound effects
* Custom wrapper instead of Electron - small file size, and little memory usage

/assets/quill-hero-2x-1630068056560.png
size: contain

---

### Quill passed the Turing test!
	It made *me* believe it was a native app.

If you're wondering where can you try this app, well, you can't.

---

### Native → Electron
	Let's make more apps that pass the Turing test!

And that's how I became Electron developer.

---

It was about the same time that I joined Reflect, which is an Electron app.


/assets/Group_1.png
size: contain

---

### How to pass the Turing test?

---

### 100ms, 50ms, 32ms rule
/assets/Group_2.png
size: contain


---

## Offline-first
	(Or at least some offline support)

Alright, so how do we make our apps fast?

---

### Offline support
	🔴 Internet required
	🟡 Some offline functionality
	🟢 Offline-first


Very few apps are built for offline-first, and I think it's time to change that.

---



/assets/DMG_Example.png
size: contain

---



/assets/Clipboard_30.png
size: contain


---



/assets/Clipboard_33.png
background: true




---

### Why offline first?
	\
	[inkandswitch.com/local-first](https://inkandswitch.com/local-first/)

---

## Speed

---

## Network optional

We go back to planes and trains, and traveling to Mars.

---

## Ownership of data

You can choose to store your data only on your computer.

---

## Ease of development
	(Time to prototype)

By far my favorite reason.


Talks about how writing all this glue code feels stupid.


---

### Prototype like you're using Rails



// ---
// 
// ```typescript
// const NotesList = () => {
// const {noteStore} = useStore()
// const notes = noteStore.findAll()
// 
// return notes.map((note) => (
// <div>
// <h1>{note.title}</h1>
// <p>{note.content}</p>
// </div>
// ))
// }
// ```

---

### From idea to execution in *hours!*
	Great for:
	* Side projects
	* Startups quickly iterating

I’m an avid side project maker. 

For startups, this is a great way to see what sticks.

---

#### Fat server, thin client (Pre-Gmail era)
/assets/fat server.png
size: contain


---

#### Fat server, fat client (most SPAs)
/assets/fat both.png
size: contain

This is where we are now! We are toiling away on both sides. 

We’re writing code on both sides. There’s some kind of database on both sides. Things can go wrong on both sides.

---

#### Thin server, fat client (offline-first)
/assets/fat client.png
size: contain

---

#### Thin server, fat client (offline-first)
/assets/not my problem.png
size: contain


---

###  Native apps have been offline-first for years
	\
	Things, OmniFocus, Bear, Ulysses, and countless others.

They started that way. And then they added sync on top.

I can vividly remember Apple’s sync framework being terrible. This tech is young.

**Stand on the shoulders of giants.**

---

## Why is it so hard in web apps?

To answer that question, we have to look at the architecture of an offline-first app.

---

### Offline-first architecture

---


/assets/Clipboard_11.png
size: contain

---


/assets/Clipboard_16.png
size: contain


---


/assets/Clipboard_14.png
size: contain


Luckily, some of these problems are solved.

React is taking care of rendering the UI and reflecting updates in the memory.

---



/assets/Clipboard_20.png
size: contain

---

###  Standard
	Core Data + CloudKit

Lucky Apple developers have a standard to use.

They can just build their offline-first app, and everything else is taken care of.


---

## Options on the web
	* Firebase
	* Replicache
	* WatermelonDB
	* LokiJS
	* RxDb
	* Dexie.js

	* IndexedDB
	* Absurd SQL
	* SQLite (WebAssembly)
	* Lovefield
	* tuple-database
	* Kikko
	* TinyBase
	* Datascript
	* SyncedStore

---

## How to pick
### 12 Questions

---

### 1. Is it modular?
	- All-in-one (Firebase)
	- Compose components (e.g. SQLite + Supabase)


Are you buying into a whole platform, or do you get to pick the best tool for each job.

When you buy into Firebase, you’re bying into their backend, their syncing engine, and their client-side database.

* There’s no perfect all in one solution.
	* Firebase is kinda close, but not really.
* Vendor lock in - what if something better comes along?
* Custom features - conflict resolution, end to end encryption 

Since there’s no perfect all-in-one solution, I would prefer to pick the perfect solution for each of the problems.

---

### There’s no good all-in-one solution for offline-first

---

### 2. Is it reactive?
	* Reactivity built-in (VLCN)
	* Just database (SQLite)

Many of the technologies have React hooks.

They give you some form of a live query.

---

### 3. What are the expectations for your code?
	- Works well with Mobx/Redux/what you’re using?
	- React hooks provided?
	- Libraries needed? (RxDB)

* I love Mobx

// ---
// 
// #### WatermelonDB:
// ```
// // This is how you make your app reactive! ✨
// const enhance = withObservables(['comment'], ({ comment }) => ({
// comment,
// }))
// const EnhancedComment = enhance(Comment)
// ```
// 
// Some of the databases I’ll be talking are made with their own idea of Reactivity. 
// 
// This doesn’t mean the database is unusuable - just that I’ll have to do a little tinkering to make it work with Mobx (or whatever reactivity framework I choose.)

// ---
// 
// #### Firebase:
// ```
// const unsub = onSnapshot(doc(db, "cities", "SF"), (doc) => {
// console.log("Current data: ", doc.data());
// });
// ```

---

### 4. What’s the approach to replication?
	* BYOB
	* Conflict resolution
		* Supports text editors?

* Replace backend to save costs
* Does it support conflict resolution? And if it doesn’t, how hard it is to add it?

To give an example here, for Reflect we started off using Firebase.

Then it turned out we needed to do conflict resolution, which we did using YJS library.

However we ended up with a lot of custom code. Firebase doesn’t support CRDTs out of the box. Actually, none of these technologies do.

The question is, how hard it is to integrate.

Usually, if the technology tries to solve all the problems for you, it’ll be harder to add something like CRDTs.

---

### 5. How does it persist the data?
	- Database size

Consider your requirements for persistence. If you’re building a to-do list apps, chances are all your data will fit into memory, and they can all be persisted in a few milliseconds.

For a usecase like that, a full database might be an overkill. 

---

### 6. Does it perform well?
	- How many queries to render a screen?
	- How complicated are your queries?


---

### 7. How do you query the data?
	- Complex queries
	- Indexes

A note-taking app, or todo-list app doesn’t need very complex queries.

However, a finance app might need much complicated queries. You might be crunching thousands of records to create a chart.

Can you build instant search with just the database?


---

### 8. Is it offline first or just capable?
	- Offline-capable (Firebase, Replicache)
	- Offline-first

For example both Firebase and Replicache aren’t really made for offline-only scenario.

Replicache promises to get better at this.

---

### 10. Can you have multiple tabs/windows?

/assets/Clipboard_34.png
size: contain



---

/assets/Clipboard_24.png
size: contain


---

####  Native:
/assets/Clipboard_26.png
size: contain



---

#### Browser/Electron:
/assets/Clipboard_23.png
size: contain

---



/assets/Clipboard_29.png
size: contain


---

#### Shared database
/assets/Clipboard_28.png
size: contain

---


#### Separate databases
/assets/Clipboard_35.png
size: contain


---

### 10. Sync or async
	- Async - Don’t block the UI
	- Sync - Blocking is actually good
	- Have to (de)serialize messages

---

### 11. Does it play well on all platforms?
	- React Native/Capacitor
		- RxDB good
		- Firebase/Replicache bad
	- Native apps (Firebase is good at this)

If you get a **really cool database on top of IndexedDb**, and it has no way of switching to SQLite, it’s gonna be a problem.

Can it use SQLite and such on React Native?

If you write it in Swift/Java, is there a similar framework for these platforms?

---

### 12. How much $?
	- Code + backend: Firebase
	- Code: Replicache, RxDB (some packages)

---

### Approaches
	1. In-memory
	2. IndexedDB
	3. In-memory + IndexedDB
	4. SQLite + IndexedDB FS
	5. SQLite + OPFS

---

## In-memory databases

FYI, I haven’t used each of these databases. I get most of my information from their documentation.

If I made a mistake, I apologize to authors.

---



/assets/Clipboard_42.png
size: contain


---

### In-memory databases
	* Loki.js
	* WatermelonDB
	* TinyBase
	* RxDB*

Both Watermelon and RxDB has interchangeable storage adapters, and I get the impression they’re **primarily made for React Native**.

The good news is: If we get SQLite running on the web, they should just work.

---

### In-memory databases
	* Extremely fast
	* Serializing the entire store (debounced)
		* 20mb is still fast

---

## IndexedDB

* doesn’t keep stuff in memory

---

### IndexedDB
	- Vanilla
	- Dexie.js
	- RxDB

---

### IndexedDB
	- Slow
	- No complex queries
	- Unreliable (Safari can wipe your data after 1 week)
	- More issues...

If your app is guaranteed to replicate somewhere, losing your data locally is not a big deal. It’ll just sync again once you’re offline.

But if your app is going to be used on Mars, it’s a big problem.

---

/assets/download-4.jpg
size: contain

---

## In-memory + IndexedDB

---

#### Replicache
/assets/Clipboard_54.png
size: contain





---

#### Custom chunking
/assets/CleanShot 2023-02-23 at 04.39.58@2x.png
size: contain


* Found a way to get the most out of IndexedDB







---

## Replicache is not offline-first (yet)

---

/assets/Clipboard_48.png
size: contain


---



/assets/Clipboard_52.png
size: contain


---



/assets/Clipboard_51.png
size: contain

* Not open-source and paid


---

## SQLite in browser
### with WebAssembly


---

### SQLite in browser
	1. SQL.js
	2. Absurd SQL
	3. Official SQLite Wasm
	4. wa-sqlite

---

#### SQL.js
/assets/Clipboard_44.png
size: contain

---

#### Absurd SQL - Actual Budget
/assets/Clipboard_45.png
size: contain


---

#### IndexedDB used as a filesystem:
/assets/idb-data.png
size: contain


---

### Origin Private File System

---


/assets/Clipboard_43.png
size: contain

---

### SQLite storage
	1. No storage
	2. **Filesystem in IndexedDB**
	3. Origin Private File System


---

### SQLite in browser
	| --- | --- |
	| SQL.js | no persistence |
	| Absurd SQL | IDBFS |
	| Official SQLite Wasm | OPFS |
	| wa-sqlite | IDBFS + OPFS |

---

### ORM/Syncing on top of SQLite
	* RxDB, WatermelonDB, etc.
	* ✨ Shiny new stuff

---

### cr-sql
/assets/Clipboard_49.png
size: contain

---

### Evolu
/assets/Clipboard_50.png
size: contain

---

## Ideal world

---



/assets/Clipboard_53.png
size: contain


---

### Thank you
	- vojto@rinik.net
	- @_vojto

