in order to run this app in its current state there are a few steps that must be followed.
First A user must start up their mysql database so that it can accept incoming connections from the Java application.
To do this they must ensure they have docker desktop downloaded and then run:

docker run -p 3306:3306 --name=cloud_vendor -e MYSQL_ROOT_PASSWORD=dummy -d mysql

from their terminal and check it is up and running, the way I prefer to do this is by downloadingMySQLWorkbench and attempting to connect to the database
with port 3306, database name cloud_vendor, username=root, password=dummy, If Hostname 127.0.0.1 does not work try 0.0.0.0.
Once you are connected ensure that the schema cloud_vendor has been automatically created, if it has not then create one yourself with the default settings (the rest will be handled when we start the app)

Once the schema is set up we can now run the app, I recommend using intelliJ to do this, navigate to DemoApplication.java and run the DemoApplication (big green play button next to line 7 if on intelliJ)
If all has gone to plan you will now be able to make a whole host of get and other requests outlined in the controller file CloudVendorController at the address
http://localhost:8080/cloudvendor
