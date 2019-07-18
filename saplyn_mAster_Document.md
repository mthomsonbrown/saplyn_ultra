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