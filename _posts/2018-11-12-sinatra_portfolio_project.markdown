---
layout: post
title:      "SINATRA PORTFOLIO PROJECT"
date:       2018-11-12 15:17:26 +0000
permalink:  sinatra_portfolio_project
---



So i have finallly completed my sinatra portfolio project. It took me longer than i had expected but thatb was not because i didn't know what i was doing. I think i started thinking bigger and wanted to make it more complex than the requirements which is cool but for the project, one should always think small(meets requirements) and add more if you have time. 


I am a soccer fan so i created a soccer app that dose the CRUD functions of creating/signing up/login(new) a user and a user can then create a team/s. A user can have many teams and teams belongs to a user. User is created with a password and username. 

The teams would have a name, stadium and a sponsor which the user can edit/update if they are the owner of the team. that is checked by using session user.id to match the user.id that is logged using helperr functions

The user can also delete their teams which they own. The user is shown the edit and delete forms only if they are the owners of the teams. 

The user can also log out of the app which will clear the session id and require the user to login again once logged out. 

I have a new favourite gem which makes creating the MVC super easy. its called Corneal. It was created by a former flatiron student. Thanks brian. Here's a link to the github repo if would like to use it https://github.com/thebrianemory/corneal


