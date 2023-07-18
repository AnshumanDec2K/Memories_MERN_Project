UI
--

=>Search, Memory Creation Form, Pagination, Memory Cards with Like and Delete functionalities
![ss2](https://github.com/AnshumanDec2K/Memories_MERN_Project/assets/91108386/dfb9eafb-9715-4276-addb-aa26da682377)

=>SignIn and SignUp window with JWT authentication and Google OAuth functionality
![ss5](https://github.com/AnshumanDec2K/Memories_MERN_Project/assets/91108386/82593be1-ddb9-493d-a0f4-a850058815b4)

=>Memory Details page with comments and memories recommendation
![ss3](https://github.com/AnshumanDec2K/Memories_MERN_Project/assets/91108386/43e467c3-290a-484a-9f82-71486381f850)


_____
Steps
-----
-> Initialised the client and server folders

-> Inside the server folder we do have the index.js file which imports all the necessary modules like express, bodyParser, mongoose, cors

-> to set the import statements in the ES6 format we add a parameter "type": "module" inside the package.json file 

-> we then initialise the express app and then use the modules imported using the app.use middleware


_____________________
Connecting to the DB:
----------------------

-> created a mongodb cluster and then a user is created and there is a connection string generated for the cluster to be connected via the node app

-> we then add the respective password and use encoding for any special charaters used in the password

-> we then do mongoose.connect(URL).then(()=>{}).catch(()=>{}) inorder to connect to the mongodb cluster

__________________________
Connecting to the routes:
--------------------------

-> creating a routes folder which houses all the express routes using the express.router()

-> we then use the controllers for the corresponding callback functions for the router.methods() like get, post, etc

-> we then import the router in the index.js file and then with the help of the use() midleware pass the route and the router 


____________
Redux setup:
------------

-> we create a reducers folder which has posts and the index file

-> In the posts reducer file we create the reducer which takes in the state and action as parameter

-> In the index reducer file we use the combine-reducer from redux and export it

-> In the main index.js file we create a store and pass in the reducer from the index reducer

-> Finally we wrap the App component within the Provider tag which takes the store as an attribute


_____________________________________
Action Creation and dispatching them:
-------------------------------------

-> We first import the use dispatch hook and then within the use effect() body dispatch the action imported

-> The useEffect changes from componentDidMount to componentWillMount in the course of execution

-> In the actions folder we then define the action creators which use redux-thunk to synchronize

-> In the action creator's definition we call the API and receive the corresponding response

-> In the action creators itself we dispatch the action with the action type and payload

-> Then in the reducer we handle the action

-> The entire flow now becomes the app component calls for the action the action is then dispatched to the reducer where it is handled


_____________________________________________________________________
Accessing the data across components from the global redux datastore:
---------------------------------------------------------------------

-> We use the useSelector hook inside the component we want to access the data in

-> The useSelector hook takes in a callback function with the state as the parameter and then accesses the payload using the dot(.) operator


______________________________
Adding file field in the form:
------------------------------
-> To add the file field in the form we use the filebase module and its tag to fetch any file in the form


________________________
For the CRUD operations:
------------------------
-> We need to add up actions and dispatch them so that we get the operations request from the backend

-> In the backend we need to create the endpoints in the controller so that the UI requests can be handled in the backend

________________
Using .env file:
----------------

-> we first need to create a .env file in the backend folder

-> we then install the dotenv node module 

-> we then set up all the required variables in the .env file 

-> in the index.js file we need to import dotenv from 'dotenv'

-> after importing the same we do dotenv.config() following the express app creation


_________________________
Google OAuth Integration:
--------------------------

-> for the ID creation we head over to "https://console.cloud.google.com/projectselector2/apis/dashboard?supportedpurview=project"

-> then go  to OAuth consent screen and then create up a project

-> after creating up the project we come to the credentials tab and create the credential for our project

-> while adding the URIs we add the URI with and without the port number

-> we also need to add up the URLs for the sites where the deployments have happened for the authentication to take place successfully

-> then the client ID provided generated is put against the clientId attribute in the GoogleOAuthProvider tag in the react App

-> the GoogleLogin tag is then wrapped within the GoogleOAuthProvider component

-> sometimes there might be error due to cache, it will work fine once the browser cache is cleared up

-> then to acess the actual credentials from the payload we use the jwt-decode npm package and then 

_________________________________________________________________________________
Keeping Track of session and accessing the Profile after successful google login:
---------------------------------------------------------------------------------

-> we use the localStorage.setItem('key', JSON.stringify()) to save the credential details for future sessional references

-> while logging out we use localStorage.clear() to remove the entries in the local storage.

___________________________________
User authentication in the backend:
-----------------------------------

-> we need to create up the routes and the controllers for the signin and signup thing

-> in both the route's controller we fetch the user by matching up the email's which is the primary key using the user model

-> for the signin controller we need to use the bcrypt.compare() to compare the entered password with the one which is associated with the user present in the db

-> if the match is successful then we use the jwt.sign() method which takes in the paramerter to be encoded along with a secret key attribute and an expires in attribute

-> for the signup controller we need to use the bcrypt.hash() method to hash the password with another attribute called salt(usually an integer denoting the degree of hashing)

-> then after creation of the hashed password we add the same as an entry inside the db

-> finally after the insertion into the db we use the jwt.sign() to create the token

____________________________________
Using the authentication middleware:
------------------------------------

-> inorder to enable the user to perform certain actions on being signed in is achieved by the authentication middleware

-> it uses the jwt.split() method to spot the encrypted jwt in the token generated

-> the obtained token is then used to verify if the passed token is fetching the correct user id associated using the jwt.verify(obtained token, secret key)

-> the google token is also decoded checking the length of the token passed which is greater than 500 

-> the middleware has a next() method which is called up once the middleware executes successfully

-> finally in the routes the auth middleware is passed after the route path to implement the same over the routes

________________________________________________
Modifications for the UI middleware integration:
------------------------------------------------

-> in the api's routes file we use the bearer token using the .interceptors.request.use() middleware

__________________
Advanced features:
------------------

-> there are some advanced features like the like and delete button will show up only over the posts created by the user

-> auto logout after the token is expired for the user

______________________________________
Search, Pagination and recommendation:
--------------------------------------

-> for all the functionality we need to create up endpoints in the backend and their respective frontend request points

-> in the frontend we need to create up actions for the same and then dispatch the actions via reducers

-> in the backend we create up the routes and their corresponding controllers 

-> for the UI changes we use the Pagination from MUI

-> we calculate the page number and the number of total number of pages along with the pages to which a particular post belongs to

-> for the search functionality we match up the tittle or the tags associated 

-> and finally for the recommendation we use the search functionality via tags to gather the recommendations


________________________
Group By Creator or Tags
------------------------

-> the user has the option to view memories from a creator's POV

![ss1](https://github.com/AnshumanDec2K/Memories_MERN_Project/assets/91108386/f29eb8e7-f938-44ec-a24a-2d745bdfc5af)

-> the user has the option to view memories by selecting the tags

![ss4](https://github.com/AnshumanDec2K/Memories_MERN_Project/assets/91108386/690b533e-126c-4e03-be5d-240506304154)








