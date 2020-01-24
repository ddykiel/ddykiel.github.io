---
layout: post
title:  "Scrunch Time"
date:   2020-01-24
excerpt: "An Android application to facillitate roommate communication"
project: true
comments: false
---

For my 2020 January Independent Study (ISP), I designed and coded a mobile application with a partner. The app is Scrunch Time, an Android application to facillitate roommate communication. 

The goals of the ISP were to write code that was clean and easily extendible, to work effectively as a team, and to document our progress. After spending three weeks on the project—the allocated time for an ISP—we created a proof-of-concept that worked for one phone.

This post deals with the general process of creating Scrunch Time, and addresses technical elements as they relate. If you're interested in the technical features of the app, check out the "ReadMe" on the GitHub. The "ReadMe" also has notes about limitations of this prototype and ideas for future prototypes.

## GitHub
[Link](https://github.com/ddykiel/ScrunchTime)

## Concept of the App

The idea for Scrunch Time came from a story many college kids—signaling to roommates that the dorm was in use, **especially** when a significant other was in the dorm. Instead of a "sock on the door," my roommates and I used a scrunchie.

But the concept for scrunch time goes farther than sexiling your roommates. Coming into college, it can be hard to communicate about your emotional needs: when you need alone time, when you're feeling social, when you want to let your roomates know you have friends in the dorm without sending a long-winded text.

I came up with the initial idea months before ISP started. I kept it on the back burner—a necessary step of any creative process—until January.

## Proof of Concept

<figure class="third">
	<img src="https://i.imgur.com/Jb1g4G4.png">
	<img src="https://i.imgur.com/o7StkFU.png">
	<img src="https://i.imgur.com/Mqat8B1.png">
</figure>

When you first get the app, you add yourself and your roommate to your room. There are five colored buttons, representing five different moods. You click the color you're feeling to communicate that to your roommate.

On the app, you can see your scrunchie with your color, and your roommate's scrunchie. The colors are as follows:

Red: Do not disturb

Purple: Knock first

Blue: Neutral

Green: Feeling social

Yellow: Friends in the dorm

You can also add up to two other roommates, for a total of four people in a room.

## Background of the App

Fall semester, I had taken Object-Oriented Design: a course that taught how to design programs and how to work in a team. I wanted to implement and expand on the design knowledge I had learned, and keep working with others—a skill essential for developers. I approached a classmate about the idea of building this mobile app. Together, we brainstormed the goals and structure of the ISP.

We recognized this ISP would involve learning and creating—with the goal of delivering a product in three weeks. I focused on the client side, i.e. the application that's on your phone. My partner focused on the server side.

## The Learning Process

With a combination of video tutorials and a textbook, *Head First Android Development,* I delved into learning the basics of Android apps. After a week or so, I was ready to get my hands dirty with the first version of the Scrunch Time prototype. As a visual learner, I drew out a general plan of how all the files would work together: which elements from layout files I would have to refer to in code files, and code snippets to do so. 

<img src="https://i.imgur.com/zLhl0dq.jpg">
    
On the back end, I thought about how we would store data about the user, their roomates, and the user's room. I drew this out as well.
    
My partner was working on servers, which I had no background experience with. During one of our meetings, he outlined the plan he had for his code. After this meeting, I drew out a representation of how his code worked. I wanted to understand it, both out of genuine interest, and to know how I should interact with his code.

## The Design Process

I made paper mockups of the application early on. After comparing the pros and cons of two approaches, I realized that a combination of both would solve most of—but not all—of our coding issues. After learning more about Android, I realized that creating multiple screens—something I had initally thought would be difficult—was actually rather easy. And I realized something I thought would be easy—dragging multiple roommates on the same screen— would be rather hard.

I often had the mockups in front of me when I was coding the app, as it helped the intangible feel more tangible.

<figure class="second">
	<img src="https://i.imgur.com/sCYefyJ.jpg">
	<img src="https://i.imgur.com/A09dQ2z.jpg">
</figure>

## Revisiting goals

### Teamwork goals

Me and my partner worked very well together—we used Trello boards to stay on track, Slack to communicate, and an individual Slack channel where we updated our progress and bookmarked resources (which was very helpful). We planned goals and deadlines during our meetings, and also learned about what the other person was doing. Our academic advisor gave us much-needed technical advice when we were stuck. He also kept us on track for deadlines and helped us scope the project more realistically, given the timeframe.

### Technical Goals

I intially wanted to use a perfect Model-View-Controller design pattern for the app. But, after researching how to do this in Android, I realized it would have been technically difficult for someone new to Android. Instead, I wrote multiple Java classes, such as "RoommateModel" and "RoomModel," to de-couple the data from the Activites classes. In this way, I had a modified MVC design pattern, where I separated out the Model, but kept the View and Controller combined. 

The server used ints instead of Strings. To communicate with the server, roommate's status had to be converted into an int. I de-coupled this into a "ServerTranslator" class, where status strings corresponded with certain integers. I wasn't sure how to de-couple the Server ID, which the server uses to identify each roommate object, from the roommate object itself. My academic advisor recommended giving each roomamte object a "Client ID," and pairing the Client IDs to the Server IDs in the ServerTransaltor class.

I utilized best coding practices, such as encapuslating code and using strings.xlm. I also wrote a "ReadMe" file and wrote (hopefully) thorough comments in my code.

### The Final Product

The app supports multiple screens and error-catching. In the three-week time window, we weren't able to get the server and client code to work together. However, on the client side, I created a background thread that runs every 30 seconds. This could be used with the server in the future, to check for a roomate's status. Since I knew how my partner's code was going to work, I called certain functions in my code and commented them out for this prototype.

#### Thank you for reading about Scrunch Time! I hope you found this reflection interesting.
