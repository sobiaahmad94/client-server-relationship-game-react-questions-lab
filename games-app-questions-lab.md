# Games App Questions Lab

Wee notes to myself:

RUNNING THE CLIENTTTTTTT
npm start - just runs the server
(do npm update if it doesn't work like earlier today)


RUNNING THE SERVERRRRR
npm run server:dev - command to run server as it aligns with what's in package.json (nodemon installed so it automatically updates... hoooooray! :) )

QUESTIONS:

# 1) What is responsible for defining the routes of the games resource?

- Seemed like a bit of an ambiguous question. I initially was looking for a wee react-router-dom import somewhere but I couldn't see that anywhere within the client side. I also couldn't see Router, Routes or Route being used so I figured maybe you're asking about the server side as opposed to the client side. (The client side could potentially use react-router-dom though so that the user could navigate through the "illusion" of pages, even though they're just "components" that are being changed but they'd technically remain on the same page as it would be a single page app.)

- After looking at the server side files, I realised that you're maybe on about the server side. In the >helpers folder there is a create_router.js file. I think the Express Router is set up using Express but it's within a function called createRouter. There's this line: const ObjectID = require('mongodb').ObjectID;
however, we didn't cover that in class. I think they're pulling mongodb which is a database though as require('express') was used and it looks like that require('') method is grasping the mongodb database? db = database. This defines the routes of the games resource, I think.

# 2) What do you notice about the folder structure? Whats the client responsible for? Whats the server responsible for? 

- (Thoughts: mate, this is like 3 in 1 questions like shampoo and conditioner 2 in 1 with glitter and sparkles sprinkled on top)

- CLIENT FOLDER
- I can see that there are two main folders - client and server. The client folder is responsible for showing what the user (aka the client) sees when they're visiting the webpage or the app or whatever. This would be all of the components on the React page and the JSX templates (HTML and JS and XML kinda language) and also some CSS for the visusals. The client side is also known as the front-end side. This is all of the user interface and stuff like that.

- SERVER FOLDER
- The server is responsible for the back-end side. Dealing with CRUD operations, like create, read, update and delete. This is where the database should be and this where Express would be used. The requests that the client gets come through to the server (it's like the client is a customer in a restaurant and has ordered pizza so the server does stuff to go get that and give it to the customer/client). APIs could be put here. Maybe it's responsible for all of the games and how the playing time, min players and max players and name can all be updated or deleted. Looks like it's a game app that stores stuff about players so maybe it's kinda their average playing time and the min players they tend to play against or they choose to play against and maximum players they choose to play against. That's what I've gathered by looking at the code and also running the client side and server side.


# 3) What are the the responsibilities of server.js?
- From looking at the server.js file, Express is first installed and then it's grabbed using require('express') then stored in a variable called express. I think the database is grabbed after. I think Express then sets up the server so that's what this file is doing. The routes are also imported. I think it's responsible for defining the routes too(like router.get('/:id'). 

- app.use(cors())
cors just makes sure that you can control what API can access a server I think. Is it to stop people hacking you? 

- *** Can someone please explain this line?
const app = express();

# 4) What are the responsibilities of the gamesRouter?
- I can't see that gamesRouter file anywhere so I'm not sure.

# 5) What process does the the client (front-end) use to communicate with the server?
- The client communicates with the server by making HTTP requests. Data can go back and forth, send and receive. So the client side like browser might be like oh I want this Pokemon data from this API so the server will be like okey dokey, the server will grab that data and give the response to the request made by the client. CRUD operations would be used as mentioned earlier. I also think the GET and POST requests would be made. GET requests are for to grab data from the server. POST requests are when a user is like commenting on their favourite funny cat video on a youtube video or something and then goes from the client to the server. I think it updates to the server. Or if on the client side someone was like oh I want to email Halsey to tell her, her writing/music is awesome then that would be a POST request. As information would be written by the client and then it would be sent to some other server and updated until it's received by the other person. I think that's how it works anyway.


# 6) What optional second argument does the fetch method take? And what is it used for in this application? Hint: See Using Fetch on the MDN docs
- I just took a look at the MDN documentation.

- Supplying request options
The fetch() method can optionally accept a second parameter, an init object that allows you to control a number of different settings. The second argument is optional as you have said in the question. But the second argument is a way to specify something like GET, POST, UPDATE or DELETE CRUD basically as well as the header and body. 
******** What's a header in this context?

- fetch grabs the URL (which is the http like http:localhost:9000)
- I then looked into what an init object actually is. request.body?


# 7) Which of the games API routes does the front-end application consume (i.e. make requests to)?

- DELETE /api/games/:id:
- There's a function called deleteGame which links to this.

- POST /api/games:
- There's a function called setGames which I think is a POST because the user can just type random stuff and in the input fields and then that's sent to the server again. I think the game gets saved in savedGame.

- GET /api/games:
- Grabs all of the games from the server as there's getGames and there's useEffect here as well then it switches to setGames state using useState I think.

- I might've missed someone but they're the ones I've noticed.


# 8) What are we using the MongoDB Driver for?

- All I know is that it's storing info to a database :S