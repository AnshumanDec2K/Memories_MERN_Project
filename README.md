# Memories_MERN_Project
 
##Steps
-> initialised the client and server folders
-> inside the server folder we do have the index.js file which imports all the necessary modules like express, bodyParser, mongoose, cors
-> to set the import statements in the ES6 format we add a parameter "type" : "module" inside the package.json file 
-> we then initialise the expess app and then use the modules imported using the app.use middleware

###connecting to the DB:
-> created a mongodb cluster and then a user is created and there is a connection string generated for the cluster to be connected via the node app
-> we then add the respective password and use encoding for any special charaters used in the password
-> we then do mongoose.connect(URL).then(()=>{}).catch(()=>{}) inorder to connect to the mongodb cluster


###connecting to the routes:
-> creating a routes folder which houses all the express routes using the express.router()
-> we then use the controllers for the corresponding callback functions for the router.methods() like get, post, etc
-> we then import the router in the index.js file and then with the help of the use() midleware pass the route and the router 

