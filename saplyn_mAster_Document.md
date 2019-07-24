# Saplyn
## This is a log of the things i'm doing to get this project built.
---

### 20190717
I'm going to try to be consistent with this thing, even if it means just 
adding entries to this log.  

I plan to restart this project as a microservice based thing.  The user 
dealings/front of the frontend I want to make in Rails, because active 
admin is pretty nice as i remember.  I can add new components to it in 
whatever language I want after that.

Because I'm making this a distributed project, this directory should 
have a collection of repositories for the separate components, and this 
document, or hopefully a prettier one later on will serve as a master log.

#### The Basic Idea
Essentially (I use that word too much) this project is planned to be a 
dashboard for personal data entries into a collection of different apps.
It should be able to sync fitbit data, alchodroid, the smoking thing, as
well as support direct entries for a variety of formats.

#### The MVP
For starters, I want to make just a basic app that can handle text entries.
This however should be a fully built slice, so it will need to include:
* user authentication (possibly a prequel to this feature)
* testing:
    * unit test 100% coverage
    * linting pass in CI
    * functional test plan
    * functional tests in automation
* documentation:
    * master document (in maybe a web frontend)
    * build, test, basic usage readme for every repository
* CI
* frontend support for:
    * web browser
    * mobile (Android only (cause I don't have an iPhone))
    * desktop?

##### The Spec (as it were) for this slice
* User should be able to add a text entry on all frontends 
* After logging in, the user should have to click at most one button 
before they can start entering text.
* The entry should be time and possibly location stamped.
* Entries should be viewable as a list.
* Entries should be private by default. Other options should be added
in the future, configurable from a menu.
* Entries should be editable and deletable.

#### First Steps
One of the first things to consider is whether to use a 
mono or multi respository structure. I'm inclined to use multiple repositories
because I want to create a psychological boundary between components, but that 
comes with some issues, particularly around integration and (this) centralized
documentation. 

As strange as it sounds, Google uses a monorepo for all their 
projects. I don't know how I feel about that. Google has some weird practices,
but it can't be denied that their software is pretty flawless. 

Still, I want to embrace distributed, so I think I'll go multi. I'm thinking 
I'll set up a central repository for (this) things like integration tests and 
whatnot, but that will serve as sort of a meta project.

---

Naming, then:

I guess I'll put this in a master-y kinda repo, and add in the integration test 
stuff here. Call it saplyn ultra or something, then have it require the other 
elements. Integration CI has to live somewhere as well, why not here. 

At some point, I'd probably want to have a separate repo for high level 
documentation, which this would go into. Then I'd have a separate repo for 
integration tests. The problem is each of these (namely the tests) would depend 
on having the whole suite of repositories available to build, but I guess if 
they're not, we found a bug.

Should I namespace everything? saplyn_web_frontend, saplyn_android_app, etc? 
Seems like a pain to navigate, and actually goes against the philosophy. Each
of the components should be independently functional and testable. That brings 
up the issue though, how do I get the "ultra" pulling all the right pieces? If 
this all lives in the public forum? I guess I'm pulling from my own namespace.
I can make a github account specifically for saplyn; not ideal if I want this 
to be in a portfolio.

### 20190723
[Edit: This blurb, for instance, I would like to tag with 
{development, saplyn, frontend, design, theory, planning, etc}]
Basically, I'm thinking of the output format sort of like a social media 
application, but it's private by default (only private for MVP(
possibly(probably) only ever private)), and searchable. So, I can add 
entries whenever I want, about whatever topic I want to write about at 
the time, and they will be timestamped and collated with the rest of 
the entries. 

I think this app, as far as an MVP, which will be a simple journaling app,
is conceived mainly as an answer to wordpress and its inability to easily
address my use case. I want to be able to make feature-rich journal entries
without a lot of extra work, and I want to be able to edit metadata defaults
easily and have tools to reason about the data entered (time, topics, etc), 
and I want that to be eventually processed by ML.

This entry I think would be well accompanied by a graph or drawing, and I'd 
also like that to be linkable to this mental spew, and also I would like to 
be able to set a reminder to create the graph on this entry at a later date.
That use case is similar to inputing raw data for something like untapped, and
setting a reminder to input it into the app, or at a more sophisitcated level,
have this app create entry data and set an alert to accept the auto-entry into
untapped.

Anyway, the development of this thing beyond hello world will need drawings, 
graphs, documents, etc. I would like to build this to the point that those 
pieces of disparate data can be managed by the core product. Until that point,
I have this MD document. I suppose I could link google drawings and whatnot 
here; not sure what the best method is of handling that stuff.

In a development scenario, do I expect this to take the place of something 
like Jira?
> Sure, why not? Jira's just a collection of entries with tags when it 
> gets to the db. Using this to the same end is just a matter of adding the right
> tags to an entry and creating views relevant to those tags.

So following up on that Jira thought, Jira is essentially just a data store with 
relevant input and output views. If I make this private by default, and add
enough richness to the in/out views, it should be able to handle journaling, 
issue tracking, test case management, personal data organization, pretty much 
everything.

The current (and also historical) paradigm of application design is that
"an application should do one thing and do it well", but most of the apps I 
use on a daily basis are nothing more than a datastore presented with custom 
views, so why not generalize the datastore and create relevant views for 
various use cases? 

I should say, I think the notion of doing one thing and one thing well makes
sense of course, modularity, separation of concerns, yada yada, but for an
actual application, I think that boils down to a microservice architecture.
The one use application ideology is presented in at least Android literature,
but I don't think that makes a ton of sense. Of course, I don't want to have to
figure out a bunch of buttons and settings to get my thing working, but in
my experience, it's a pain to have to navigate through a bunch of different 
apps to track the things I want to (calories, cigarettes, alcohol, exercise, 
sleep, etc). 

I want to make one app that tracks all that data, and have views 
available to that apps users that can be summoned with one or two clicks that
present the relevant interface. That way, all the data can be correlated with
each other, and there's one central point of security for the users data.

{Call to action}
Again, this is a pile of words that I may never go back and read, but it's
important input to the design of this project, so it would be nice if at
least the MVP could help organize this into something easier to digest later,
and possibly alert the creator (me) that other materials might be useful 
to develop, a diagram, drawing, something like that.