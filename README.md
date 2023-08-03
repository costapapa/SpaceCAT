# SpaceCAT

Description:

Our first group project on the General Assembly Immersive bootcamp involved creating Full Stack Web Application. For this project the requirement was to use Python and Django Frameworks.

Deployment:
https://space-cat.fly.dev/

Timeframe & Working Team:
We were given a week to complete our Web Application, we were assigned into a group of three. Myself, Amrit and Trung. Hence the name Space C(osta)A(mrit)T(rung)

Technologies:
Django Frameworks, Python, PostgreSQLVisual Studio Code.

Brief:
☐ Connect to and perform data operations on a PostgreSQL database (the default SQLLite3 database is not acceptable).
☐ If consuming an API (OPTIONAL), have at least one data entity (Model) in addition to the built-in User model. The related entity can be either a one-to-many (1:M) or a many-to-many (M:M) relationship.
☐ If not consuming an API, have at least two data entities (Models) in addition to the built-in User model. It is preferable to have at least one one-to-many (1:M) and one many-to-many (M:M) relationship between entities/models.
☐ Have full-CRUD data operations across any combination of the app's models (excluding the User model). For example, creating/reading/updating posts and creating/deleting comments qualifies as full-CRUD data operations.
☐ Authenticate users using Django's built-in authentication.

Planning:
We chose to use the NASA API as we were all excited with understanding more about space and looking at NASA’S pictures of the day we found that all the images would be amazing to work with.
The first thing we did was designate some responsibilities amongst each other. I would be in charge of User Stories and the Trello Board. Amrit would create the ERD Models and Trung would create the wire frames.

During the planning process we sketched out our Wireframe using Excalidraw:

<img width="567" alt="Screenshot 2023-08-03 at 16 00 32" src="https://github.com/costapapa/SpaceCAT/assets/130251744/2a8e1879-2a30-444a-af45-bf4cbfb76eee">

I then created a Trello board with user stories, the user stories would then be used for smaller bitesize tasks in our project.

<img width="613" alt="Screenshot 2023-08-03 at 16 04 53" src="https://github.com/costapapa/SpaceCAT/assets/130251744/c3bff575-d1fb-46c6-b419-fe4356426b85">

Finally our ERD with our models:
<img width="602" alt="Screenshot 2023-08-03 at 16 06 32" src="https://github.com/costapapa/SpaceCAT/assets/130251744/53ce8568-be74-44f3-8d14-4f2d045caf25">

We then designated tasks for each person in the group.

Trung was designated to do the Styling, Amrit would be responsible for the Database and Models. My role was to ensure the API integration and understand how they worked as currently we had no lesson on how to extract object information from an API and render on a web page. The night before the project I spent the night coding and trying to get our chosen API (NASA Picture Of The Day) to render on the page. As I had more experience in JavaScript I chose to try and first render the API using Javascript, once I understood the basics I could translate this to Python Language. 

Code process:

As this was the first time Amrit and I used API’s we wanted to tackle this first. Luckily the night before I was able to render the NASA API through Javascript so once we had translated the code into Python we successfully got the NASA picture of the day to render on the page. This was the highlight moment for me in the project. I wish I had a screenshot of our camera footage of when it happened. We let out the biggest cheer! Please see below screenshot of the code used to render the API and visually what it looked like:

<img width="535" alt="Screenshot 2023-08-03 at 16 07 36" src="https://github.com/costapapa/SpaceCAT/assets/130251744/1d6bcc5e-4f4b-41f2-b193-49d5d7c37cf4">

<img width="440" alt="Screenshot 2023-08-03 at 16 07 50" src="https://github.com/costapapa/SpaceCAT/assets/130251744/9b2efe2b-a5a2-4dd2-a341-b6ddbfe488dd">

<img width="623" alt="Screenshot 2023-08-03 at 16 08 06" src="https://github.com/costapapa/SpaceCAT/assets/130251744/1631a4ad-aa62-4e4c-ac04-a5c0ea351792">

Once we had the API rendering on our page we then created some models as ultimately we wanted our User to save the  Nasa Apods to their album. Please see the models we created below:

<img width="468" alt="Screenshot 2023-08-03 at 16 08 28" src="https://github.com/costapapa/SpaceCAT/assets/130251744/19227e42-2e01-4d03-a466-378c6ab00a90">

<img width="512" alt="Screenshot 2023-08-03 at 16 09 57" src="https://github.com/costapapa/SpaceCAT/assets/130251744/89dbbfc2-84d5-4a8b-bfdb-3922b11ac192">

Once the model was created we wanted to add the ability for our users to edit or delete their album. Django includes a very nice way of doing this by using Class Based Views(screenshot below).

<img width="386" alt="Screenshot 2023-08-03 at 16 10 31" src="https://github.com/costapapa/SpaceCAT/assets/130251744/aa9dde0e-3d54-4935-be1a-9fc801cc3dfb">

Please also see some of the paths(urls) we created, which route our navigation:
<img width="604" alt="Screenshot 2023-08-03 at 16 11 00" src="https://github.com/costapapa/SpaceCAT/assets/130251744/d18a7bca-c541-45a3-96c2-0804b6e8db0c">

Our next main focus, and perhaps the hardest part of our project was to save the apods(picture of the day) to the albums. We wanted our user to select a date on the datepicker and once the Picture was fetched from the API there would be another button to save the picture to your albums. 

The main issue we had with this was that our API did not have any POST methods, so I had to think of a different way to ensure a way I could get to save the picture to our Albums. After a day and half I decided to create two similar forms. One would GET the picture from the API and the other would save it to the albums. A way I got this to work would be one form would remain on the screen at all times and the other we would hide the datepicker. 

<img width="611" alt="Screenshot 2023-08-03 at 16 11 23" src="https://github.com/costapapa/SpaceCAT/assets/130251744/62c80eeb-66c4-4b4b-9161-69f2bebf9ad1">

<img width="615" alt="Screenshot 2023-08-03 at 16 11 46" src="https://github.com/costapapa/SpaceCAT/assets/130251744/ada83cf0-8943-46eb-ad91-c2893456159f">

Here is our apod save function below, we used the Apod.Objects.create method to save the image date and create an object in our database with the information extracted from the API:

<img width="610" alt="Screenshot 2023-08-03 at 16 12 10" src="https://github.com/costapapa/SpaceCAT/assets/130251744/275bb5da-0afa-4cc0-9412-5bb6d2f9061b">

<img width="613" alt="Screenshot 2023-08-03 at 16 12 26" src="https://github.com/costapapa/SpaceCAT/assets/130251744/6e539e47-d9f7-4308-949e-68ca4d078169">

Once the picture was saved, the user could then add it to any album they wanted by using the add button. Screenshot below:
<img width="610" alt="Screenshot 2023-08-03 at 16 13 04" src="https://github.com/costapapa/SpaceCAT/assets/130251744/76e26e77-fbdc-4095-9019-45eb09f5cbbd">

<img width="441" alt="Screenshot 2023-08-03 at 16 13 19" src="https://github.com/costapapa/SpaceCAT/assets/130251744/2b3c7c14-5e78-4e0c-83e9-fced4be401c3">

<img width="622" alt="Screenshot 2023-08-03 at 16 13 36" src="https://github.com/costapapa/SpaceCAT/assets/130251744/e2878c03-9974-47c0-af67-8ab1a78f25d9">

The backbone of our app was now complete and we spent the remaining day or two refining everything and styling the app in the way we wanted it to look. We also wanted to make the app mobile friendly and Bootstrap helped with this. 

Once we had all the pictures saved into an album they were displayed in cards, I wanted to add a feature where the user could click on an image preview and a modal would pop up. As we were using Bootstrap this was quite easy to implement:

<img width="424" alt="Screenshot 2023-08-03 at 16 13 59" src="https://github.com/costapapa/SpaceCAT/assets/130251744/46a01da0-6553-4126-a275-8eae51e6743f">

We spent the last day really refining the styling. I consulted with Amrit on the design of the logo and the about page, then he executed the design.


We spent the last day really refining the styling. I consulted with Amrit on the design of the logo and the about page, then he executed the design.

An additional feature I wanted to add at the end was to have the Pictures saved in the database on our homepage, so users could click on them and if they liked them could save them. Adding this would make the user experience more interactive, I felt it would draw the user in.

I added this to the homepage function screenshot below:

<img width="467" alt="Screenshot 2023-08-03 at 16 16 12" src="https://github.com/costapapa/SpaceCAT/assets/130251744/0ff6d8b1-5879-41c2-bd5e-6efd8b2be15f">

As the apods were already saved in the database this would mean we would not need to request the information from the API on the homepage, they would just display a random picture everytime you hit the home page. If a user clicked the image on the homepage this would render a redirect to the Details page of the picture:

<img width="609" alt="Screenshot 2023-08-03 at 16 16 37" src="https://github.com/costapapa/SpaceCAT/assets/130251744/bfa3fd89-8643-449e-8e2a-f4f450d959c1">

<img width="588" alt="Screenshot 2023-08-03 at 16 17 17" src="https://github.com/costapapa/SpaceCAT/assets/130251744/58c98e76-ddc8-4bcf-ab09-98602fa212ff">

<img width="604" alt="Screenshot 2023-08-03 at 16 17 30" src="https://github.com/costapapa/SpaceCAT/assets/130251744/90faf758-9a0a-4a3c-b54a-e4a417256b4c">

On the morning of our presentation which was due to be held at 1pm. We spent the morning sharing screens and going through any details we wanted to shape up. There were a lot of fiddly bits but ultimately this helped us give a polished and fully finished  project. 

Challenges:
Saving the API picture to an album, as mentioned above. 
Working in a team was also very hard at some points, one of our team members would prefer to work into the early mornings, this took a lot of adjustment. Working differently next time I would ensure we had certain times that we would all be working at the same time.

Wins:
Mobb programming! I loved working alongside Amrit, we bounced ideas off each other and helped each other solve problems much quicker than if we were working solo. 

The app being mobile friendly, and the styling had a nice space theme throughout. This added a nice finishing touch and really made the app more fluid.

Key Learnings:
Learning how to use a different coding language like Python, which even though I did not have much experience in. It felt really nice learning something from scratch and applying the fundamentals I learnt on the course so far and transferring them over to Python. As a developer I now understand that anything can be learnt and I will be constantly learning everyday for the rest of my career.

Bugs:
Sometimes the API does not work as smoothly as we hope, unfortunately this is not something we can fix as we do not have control over the API. 

Future Improvements:
Originally we wanted our app to track different satellites from a different NASA Api, as we took quite a while to get the APOD API working this goal was not achievable. A week is a pretty short time to create an APP. This is something I would love to revisit one day. Perhaps with Amrit! 































