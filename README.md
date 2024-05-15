mongodb: A mongodb database is needed for this. https://www.mongodb.com/docs/guides/

ruuvitag_node.js: Run with this command in cmd 'node ruuvitag_node.js' Put this in the web browser 'http://localhost:8080/ruuvitag_website.html'

'Add' appends data to the chart and scales it between the min and max values.
'Delete' deletes all data from the charts.

ruuvitag_haku.py: Gets data roughly every 10 seconds in the json format from the ruuvitags. When enough data is received, it's sent to the mongodb database.

=================================================================

MongoDB

Downloads:
    For ruuvitag_haku.py:
        (python -m pip install ruuvitag-sensor) or (py -m pip install ruuvitag-sensor)
        pip install requests
    For ruuvitag_node.js:
        npm install mongodb

- To create a new project database in MongoDB:
    1. Create a new project in mongoDB for database. Name your project anything you want and click on "Next" then "Create Project".
    2. In the left "Overview" section, create a cluster by clicking on the "Create" button. To deploy your cluster, select the "Free" cluster option then name it whatever you want. Finally, click on "Create Deployment" to finalize the process.
    3. Add a connection IP address, then create your database user. Once completed, click on the "Create Database User" button. Finally, select "Choose a connection method" to proceed.
    4. To connect your cluster, find the "Connect to your application" section then select "Drivers" to follow the instructions. (Remember to run the command "npm install mongoDB" in your terminal).
    5. Once you have completed the intructions, in the left "DEPLOYMENT" section, click on the "Database". You should find your cluster that you created. Click on the "Browse Collections", then create your own data by clicking on the "Add My Own Data". Finally, name your database and collection, and you're done! Congratulations, you have created your database!

- To create a API key for your database in MongoDB:
    1.  In the left "SERVICES" section, click on the "Data API". Then select your cluster and, finally click on "Enable Data Access from the Data API" button. 
    2. In the "Create your Data API Key" section, name your API Key, then click on the "Generate API Key" button. Remember to save your API Key and store it in a secure location. 
    3. In the "Copy snippet into your code" section, select your database and collection name to ensure that your database/script is working properly. Congratulations, you have created an API Key!

- To create a Data API URL Endpoint (once you have created an API Key):
    1. In the left "SERVICES" section, click on the "Data API".
    2. Click on "settings" in the "Data API" navigation bar.
    3. Scroll down and look for "View Advanced Settings", then click on it. 
    4. Click on the "Continue to App Services" button.
    5. Click on "HTTPS Endpoints" in the "Custom HTTPS Endpoints" navigation bar.
    6. Click on "Add an Endpoint" button.
    7. Give the endpoint a name "/action/findOne". You will need to repeat these steps to create another Data API URL Endpoint named "/action/insertOne" after you have created "/action/findOne" endpoint first. (The order of creation doesn't matter.)
    8. Once you have completed the steps above, scroll down and look for "FUNCTION". Then, select "resetFunc", and finally click on "save" button at the bottom. In the "ENDPOINT SETTINGS", copy the (URL) and put it in ruuvitag_node.js for the "findOne" endpoint and ruuvitag_haku.py for the "insertOne" endpoint URL. Congratulations, you have created a Data API URL Endpoint!
    - For example, "findOne" should look like this: "https://eu-central-1.aws.data.mongodb-api.com/app/data-(YourData)/endpoint/action/findOne" and "insertOne" should look like this: "https://eu-central-1.aws.data.mongodb-api.com/app/data-(YourData)/endpoint/action/insertOne".

=================================================================

Credits:
    Former teams:
        First team (up to 15 April 2024):
            Ramin Ahmadi
            Mikael Kalle Johannes Nyman
            Tiitus Heikki Juhani Merikallio
        Second team (15 April 2024 - 15 May 2024):
            Satvik Velpula
            Than Ngoc Quang
            Mikhail Kryukov
            