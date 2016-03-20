# MongoDB

## Creating the Database ##

The following instructions expect that the `bin` directory of `MongoDB` is in your `PATH`. If you do not have this
directory in the `PATH`, simply write the full location to the binaries.

Choose a directory to store your database (ie. `./data/db`). Then open a terminal in this directory:  
````bash
$ mongod --storageEngine wiredTiger --dbpath . --port 27017
````

While this process is running, open an other terminal to configure the access to the database. We will create two users:
* The first one will be used for the administration of the DB.
* The second user will be used by the application. The application will run with restricted privileges.

Enter the mongo shell with:  
````bash
$ mongo localhost:27017
````
Now, the following commands will create the users we need:
````txt
> use admin
> db.createUser({user: "root", pwd: "rootPwd", roles: ["root"]})
> use main
> db.createUser({user: "app", pwd: "appPwd", roles: ["readWrite"]})
````

Once you're done you can close the mongo shell and the mongo daemon.
