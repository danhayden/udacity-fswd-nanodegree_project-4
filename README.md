App Engine application for the Udacity Nanodegree: Full Stack Developer (Project 4)

## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]
- [API Explorer][7]

## Setup Instructions
1. Update the value of `application` in `app.yaml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
1. Update the values at the top of `settings.py` to
   reflect the respective client IDs you have registered in the
   [Developer Console][4].
1. Update the value of CLIENT_ID in `static/js/app.js` to the Web client ID
1. (Optional) Mark the configuration files as unchanged as follows:
   `$ git update-index --assume-unchanged app.yaml settings.py static/js/app.js`
1. Run the app with the devserver using `dev_appserver.py DIR`, and ensure it's running by visiting your local server's address (by default [localhost:8080][5].)
1. (Optional) Generate your client library(ies) with [the endpoints tool][6].
1. Deploy your application.

## Tasks

## Task 1: Add Sessions to a Conference

### Define the following Endpoints methods

- `getConferenceSessions(websafeConferenceKey)`
   Given a conference, return all sessions

- `getConferenceSessionsByType(websafeConferenceKey, typeOfSession)`
   Given a conference, return all sessions of a specified type (eg lecture, keynote, workshop)

- `getSessionsBySpeaker(speaker)`
   Given a speaker, return all sessions given by this particular speaker, across all conferences

- `createSession(SessionForm, websafeConferenceKey)`
   Open only to the organizer of the conference

### Define Session class and SessionForm

In the SessionForm pass in:
- name
- highlights
- speaker
- duration
- typeOfSession
- date
- start time (in 24 hour notation so it can be ordered)

### Explain your design choices

The Sessions implementation is based heavy on the existing Conference
implementation due to their similar functionality and related purpose.

For the sake of simplicity speaker is defined as a StringProperty to avoid the
need create a separate speaker entity.

## Task 2: Add Sessions to User Wishlist

### Define the following Endpoints methods

- `addSessionToWishlist(SessionKey)`
   adds the session to the user's list of sessions they are interested in attending

- `getSessionsInWishlist()`
   query for all the sessions in a conference that the user is interested in


## Task 4: Add a Task

### Define the following Endpoints method

- `getFeaturedSpeaker()`
   When a new session is added to a conference if there is more than one session
   by this speaker return featured speaker / sessions from memcache.


[1]: https://developers.google.com/appengine
[2]: http://python.org
[3]: https://developers.google.com/appengine/docs/python/endpoints/
[4]: https://console.developers.google.com/
[5]: https://localhost:8080/
[6]: https://developers.google.com/appengine/docs/python/endpoints/endpoints_tool
[7]: https://apis-explorer.appspot.com/apis-explorer/?base=https://udacity--conference-central.appspot.com/_ah/api#p/
