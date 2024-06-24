# Location-based-search-
a website that gives location-based ameneties using node js and web scrapping using puppeteer API 


server.js
This is the server-side code that handles the form submission and interacts with Google Maps using Puppeteer.
Here's a breakdown of the server.js code:
1.We require the 'Express' and 'Puppeteer' libraries.
2.We create an Express app and set up the server to listen on port 3000.
3.We define a variable 'city' to store the user-input city name.
4.We use the 'express.json()' and 'express.urlencoded({ extended: true })' middleware to parse JSON and URL-encoded data in the request body.
5.We define two routes: 'app.get('/')' and 'app.post('/')'.

app.get('/')

This route handles GET requests to the root URL ("/"). It simply sends the index.html file to the server.

app.post('/')

This route handles POST requests to the root URL ("/"). It's where the magic happens!

Here's what happens when the user submits the form:
1.We extract the city name from the request body using req.body.city.
2.We launch a new instance of Puppeteer using 'puppeteer.launch({ headless: false })'. The 'headless: false' option allows us to see the browser in action.
3.We create a new page using browser.newPage().
4.We navigate to two different Google Maps search URLs using page.goto(). The URLs are constructed by concatenating the city name with a fixed URL template. The first URL searches for restaurants, and the second URL searches for hospitals.
5.We send a response back to the client with a success message indicating that the search results are available for the specified city.
6.If any errors occur during the process, we catch them and send a 500 error response with an error message.

That's it! When you run the server and open the index.html file in a browser, you can enter a city name and click the "Search" button. The server will launch a new instance of Puppeteer, navigate to the Google Maps search URLs, and send a response back to the client.

