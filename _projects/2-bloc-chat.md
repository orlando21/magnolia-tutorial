---
layout: project
title: Angular Chat
thumbnail-path: "../img/ng-chat.png"
short-description: Chat in real time with your friends using this single page application implemented in AngularJS.
github-repository: orlando21/ng-chat
demo-url: https://ng-realtime-chat.herokuapp.com

---
I developed Angular Chat during Bloc's [frontend development course](https://www.bloc.io/frontend-development-bootcamp). The app allows users to create chat rooms and discuss in real time. After opening the page, a user is prompted for their name and can choose any of the rooms on the left side to join a discussion. There's also an option to create new rooms.

### Method

The project was built in HTML5, Bootstrap CSS, AngularJS 1.4.7, and Firebase 2.2.4 from a set of user stories I had written.

### Challenge

This project was my first experience with using the cloud provider [Firebase](https://www.firebase.com/) to store and retrieve data in real time. At the end of the project I deployed the app on [Heroku](https://www.heroku.com/).

### Solution

Below are the main steps taken to implement the app.

#### 1. Configuration

Configuration steps were similar to those used in [Bloc Jams](http://gregbabb.com/projects/2-bloc-chat.html). I set up Bloc's [Frontend Project Starter](https://github.com/Bloc/bloc-frontend-project-starter) and made sure that dependencies were installed in anticipation of later deploying on Heroku (Heroku has a very low tolerance for improperly installed dependencies).

I set up the app's look & feel by downloading a Bootstrap CSS template featuring top and left sidebars (these would later come in handy for implementing the app's title and room list respectively).

In addition, I set up user accounts with Firebase and Heroku, which were both free of charge for my purposes.

#### 2. Creating and storing chat rooms

Rooms are stored as objects (JSON format) in Firebase, which offers its AngularFire binding for applications. This means your app can synchronize objects and data stored in Firebase in real time. Of particular interest was AngularFire's `$firebaseArray` service, which allowed me to handle rooms and messages stored in Firebase as arrays.

Below you see how rooms are stored in Firebase: each room is an object denoted by a randomly assigned `$id` and a single property for the name.
{:.center}
![]({{ site.baseurl }}/img/firebase_rooms.jpg)

Rooms and messages can each be handled via Firebase's `child()` method.

{% highlight javascript %}
var firebaseRef = new Firebase("<FIREBASE_API_URL>");
var rooms = $firebaseArray(firebaseRef.child('rooms'));
{% endhighlight %}

I created an Angular `Room.js` factory to provide an array of rooms retrieved from Firebase. Controllers request the `rooms` array from the factory to display or change the data of the room objects in Firebase.

Modals (e.g., for creating chat rooms) are implemented via UI Bootstrap's `$uibModal` service and a controller dedicated to creating rooms.

#### 3. Setting up messaging

Messages are stored and manipulated in both the app and in Firebase in a similar way as chat rooms, as described above. I added a `room.$id` property to each message in Firebase to associate it to a room.

When a user clicks on a room in the left sidebar, associated messages are displayed in the main container. I created a `Message.js` factory to load and synchronize Firebase messages for a controller to display or change.

#### 4. Users

When a user first displays the app, a modal prompts for username. A username is stored as a string in locally stored Angular cookie (`ngCookie`). When the app is re-opened at a later time, it retrieves the username data in the cookie and doesn't prompt for username.

As the app needs to detect the existence of the cookie as soon as it's run, the code for this is contained in a `run()` block in the main Angular module. A property for `username` is added to every message in Firebase to associate messages with users.

#### 5. Migrating to Firebase 3

With Google's acquisition of Firebase last year, Firebase's Dashboard UI has been upgraded as well. Recently I migrated the app to the next iteration of Firebase. Initially I had some trepidation but it went smoothly once I figured a few things out.

First, I "upgraded" the versions of Angular (still in v1 though), Firebase, and Angularfire by simply changing version numbers in `index.hmtl`:

{% highlight javascript %}
<!-- JS scripts: Angular & jQuery -->
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.0/angular.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.6.0/angular-cookies.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/angular-messages/1.6.0/angular-messages.min.js"></script>
<script src="https://code.jquery.com/jquery-2.1.3.min.js"></script>

<!-- AngularUIRouter -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/angular-ui-router/0.3.2/angular-ui-router.js"></script>
<!-- Firebase -->
<script src="https://www.gstatic.com/firebasejs/3.6.2/firebase.js"></script>

<!-- AngularFire -->
<script src="https://cdn.firebase.com/libs/angularfire/2.2.0/angularfire.min.js"></script>
<script src="https://www.gstatic.com/firebasejs/3.6.2/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/3.6.2/firebase-auth.js"></script>
<script src="https://www.gstatic.com/firebasejs/3.6.2/firebase-database.js"></script>
<script src="https://www.gstatic.com/firebasejs/3.6.2/firebase-messaging.js"></script>
{% endhighlight %}

As can be seen, I also added references for features I don't use, like `firebase-auth`, etc. (who knows these might be handy in the future).

The old `var ref = new Firebase("https://databaseName.firebaseio.com")` has been deprecated in favor of the idea of initializing the Firebase app locally once (which I include in `index.hml`):

{% highlight javascript %}
var config = {
apiKey: "apiKey",
authDomain: "projectId.firebaseapp.com",
databaseURL: "https://databaseName.firebaseio.com"
};
firebase.initializeApp(config);
{% endhighlight %}

See the [Firebase upgrade guide](https://firebase.google.com/support/guides/firebase-web) for more information.

Next, I added new code in the two factory services respectively:

{% highlight javascript %}
// Room.js
var rootRef = firebase.database().ref();
var rooms = $firebaseArray(rootRef.child('rooms'));

// Message.js
var rootRef = firebase.database().ref();
var messages = $firebaseArray(rootRef.child('messages'));
{% endhighlight %}

And that's it.

### Lessons

This project provided the opportunity to get into the mechanics of using a third-party API like Firebase. I learned what it took to bind Firebase's services to an Angular app. Despite Firebase's marketing about ease of use, I nevertheless found it challenging to understand and use it at first. The fact it stores objects in JSON format would seem to provide immediate ease of use, but it wasn't easy in the beginning to manually populate the database with objects in correct JSON format, and Firebase's UI didn't seem so intuitive for manually adding data either.

As always in coursework there are time constraints. Had I had more time, I would have added user authentication (in Firebase) and made improvements to scrolling when the space taken by messages exceeds the length of the viewport.

As it was, I could take the knowledge gained here and apply in my Capstone project [Angular Help Viewer](http://gregbabb.com/projects/3-help-viewer).
