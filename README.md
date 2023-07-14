# Memories_MERN_Project

Steps

-> initialised the client and server folders

-> inside the server folder we do have the index.js file which imports all the necessary modules like express, bodyParser, mongoose, cors

-> to set the import statements in the ES6 format we add a parameter "type" : "module" inside the package.json file 

-> we then initialise the expess app and then use the modules imported using the app.use middleware



#connecting to the DB:

-> created a mongodb cluster and then a user is created and there is a connection string generated for the cluster to be connected via the node app

-> we then add the respective password and use encoding for any special charaters used in the password

-> we then do mongoose.connect(URL).then(()=>{}).catch(()=>{}) inorder to connect to the mongodb cluster




#connecting to the routes:

-> creating a routes folder which houses all the express routes using the express.router()

-> we then use the controllers for the corresponding callback functions for the router.methods() like get, post, etc

-> we then import the router in the index.js file and then with the help of the use() midleware pass the route and the router 



Redux setup:
-> we create a reducers folder which has posts and the index file

-> In the posts reducer file we create the reducer which takes in the state and action as parameter

-> In the index reducer file we use the combine-reducer from redux and export it

-> In the main index.js file we create a store and pass in the reducer from the index reducer

-> Finally we wrap the App component within the Provider tag which takes the store as an attribute



Action Creation and dispatching them:

-> We first import the use dispatch hook and then within the use effect() body dispatch the action imported

-> The useEffect changes from componentDidMount to componentWillMount in the course of execution

-> In the actions folder we then define the action creators which use redux-thunk to synchronize

-> In the action creator's definition we call the API and receive the corresponding response

-> In the action creators itself we dispatch the action with the action type and payload

-> Then in the reducer we handle the action

-> The entire flow now becomes the app component calls for the action the action is then dispatched to the reducer where it is handled



Accessing the data across components from the global redux datastore:

-> We use the useSelector hook inside the component we want to access the data in

-> The useSelector hook takes in a callback function with the state as the parameter and then accesses the payload using the dot(.) operator



Adding file field in the form:
-> To add the file field in the form we use the firebase module and its tag to fetch any file in the form



For the CRUD operations:

-> We need to add up actions and dispatch them so that we get the operations request from the backend

-> In the backend we need to create the endpoints in the controller so that the UI requests can be handled in the backend


Using .env file:

-> we first need to create a .env file in the backend folder

-> we then install the dotenv node module 

-> we then set up all the required variables in the .env file 

-> in the index.js file we need to import dotenv from 'dotenv'

-> after importing the same we do dotenv.config() following the express app creation



Google OAuth creation:

-> for the ID creation we head over to "https://console.cloud.google.com/projectselector2/apis/dashboard?supportedpurview=project"

-> then go  to OAuth consent screen and then create up a project

-> after creating up the project we come to the credentials tab and create the credential for our project

-> while adding the URIs we add the URI with and without the port number

-> then the client ID provided generated is put against the clientId attribute in the GoogleOAuthProvider tag in the react App

-> the GoogleLogin tag is then wrapped within the GoogleOAuthProvider component

-> sometimes there might be error due to cache, it will work fine once the browser cache is cleared up

-> then to acess the actual credentials from the payload we use the jwt-decode npm package and then 


Keeping Track of session and accessing the Profile after successfull google login

-> we use the localStorage.setItem('key', JSON.stringify()) to save the credential details for future sessional references

-> while logging out we use localStorage.clear() to remove the entries in the local storage.


