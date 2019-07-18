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