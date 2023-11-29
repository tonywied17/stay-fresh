# Creating an AWS RDS

This guide will tell you how to set up your free tier AWS RDS. You will be using this as your database for projects 0 and 1 if you don't set up a local Postgres database, and you will be using it for project 2 so that your entire group has access. RDS is a service for hosting a relational database in the cloud using AWS.

**Note: Make sure that you only create ONE database and only have ONE running at a time to avoid charges.**

## Creating and Configuring your RDS

1. Log in to the [AWS console](https://aws.amazon.com).
2. On the top of the page, click "Services".
3. Choose "Database" then go to "RDS".
4. Under "Resources", click on "DB Instances (0/40)".
5. On the right side of the page, click the orange button that says "Create database".
6. Under "Engine options", choose "PostgreSQL".
7. Under "Version", choose "PostgreSQL 12.5-R1".
8. Under "Templates", choose "Free tier". *This is very important to make sure that you don't get charged money for your RDS.*
9. Under "Settings", "DB instance identifier", give your database a name. This database will be used throughout all of training, so name it something general.
    - I recommend that you name it in lowercase letters with hyphens between words, as this is the standard convention.
10. Under "Credentials Settings", you can leave "postgres" as the master username, but create a Master password and **be sure to write it down so that you don't lose it or forget it.**
11. Go down to "Connectivity" and find "Public access", then check "Yes".
12. Finally, go down to "Create database" at the bottom of the page. If you chose "Free tier" in step 8, all settings should be automatically set to the free option so you don't need to change anything that we skipped here.
13. Wait a few minutes for your database to finish creating. You might need to refresh until the "Status" column changes from "Creating" to "Running".
14. Click the name of your database to view its information.
15. Go down to "Security group rules" and click on a Security group.
16. Click on the Security group ID that appears.
17. Click on the "Edit inbound rules" button on the right side of the page.
18. If there are any rules already there, change the "Source" drop down to "My IP".
    - *Note: if you have irregular IPs or they change often, you may need to come back and change this as needed. However, you still want to keep the rule rather than have your RDS open, as people do try to hack into these RDS instances.*
    - *If you have multiple locations that you work from (for instance, I work from home and from the office), you can create multiple rules so that you have one for each IP.*
19. Click "Add rule" and change the "Type" drop down to "PostgreSQL" then change the "Source" drop down to "My IP".
20. Click "Save rules" on the bottom right.

## Connecting to your RDS with DBeaver

1. Go back to the RDS Management Console for your database.
2. Under "Connectivity & Security" and "Endpoint & port", copy the Endpoint.
3. In DBeaver, click on the symbol below "File" that looks like a plug with a little plus sign.
4. Choose PostgreSQL and make sure that Connection View has "Advanced" checked at the bottom, then click Next.
5. Paste the endpoint you copied in step 2 into the "Host" input.
6. "Database" can be whatever you want to name this database. It is postgres by default.
7. Enter in the master username and password that you created earlier. Remember, if you didn't change the password, it will just be "postgres". You can find the master username in the RDS Management Console if you forget it, but you can't do the same with the password, which is why it was very important to write it down.
8. Click "Test Connection" to see if everything is correct. If you get a Network IO Error, it is likely that you need to go back to steps 14-20 above. If that doesn't work, make sure the endpoint/host is entered correctly.
9. Click "Finish" and you'll be successfully connected to your database.
    - *Note: you'll be connected to the public schema by default, but you'll probably want different schemas for each project, so before you run any DDL/DML, make sure that you're connected to the right schema. There is a dropdown at the top that will say `schema_name@db_name` that will tell you where you're running scripts.*
10. In order to write/run scripts, you can open up a SQL Editor with the button under "Search" that looks like a little paper script with a plus sign (if you hover over it, it says New SQL Editor).

## Deleting an RDS Instance

You may want to do this if you want to create a new one (since you should only ever have one to avoid charges) and you also will likely want to do this at some point after training to avoid charges for a database that you're not even using.

1. Go to the RDS Management Console for your database. (Database->RDS->DB Instances(1/40)->db-name)
2. Drop down "Actions" on the top right.
3. Choose "Delete".
    - Stop will not work - a stopped RDS instance restarts after a certain amount of time.
4. You can choose to create a final snapshot if you want to, but you probably don't need to unless you plan to create this database again in its current state, so you can uncheck that box.
5. Type the message in the box to confirm deletion, then click "Delete".