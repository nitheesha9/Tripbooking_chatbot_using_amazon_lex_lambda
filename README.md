# Tripbooking_chatbot_using_amazon_lex_lambda
ABSTRACT:

The Trip Booking Chatbot using Amazon LEX and LAMBDA aims to simplify the process of booking trips for users. The chatbot, powered by Amazon Web Services, allows users to interact with a conversational interface that can understand natural language and provide relevant responses. The chatbot uses Amazon Lex to process user input and extract relevant information, and Amazon Lambda to execute business logic and integrate with external systems. With this chatbot, users can easily book cars and hotels.

IMPLEMENTATION:

LEX

Step 1:

Sign in to the AWS Management Console and navigate to the Amazon Lex console.

Step 2:

Click "Create" under "Chatbots". Choose “BookTrip” blueprint. Leave the default bot name (BookTrip). Click Create.

Step 3:

The console shows the BookTrip bot. On the Editor tab, review the detailes of the preconfigured intents (BookCar and BookHotel).Save the intent. Click on Build option. Now BookTrip build was successful. Test your bot in the console to make sure it works.

LAMBDA

Step 4:

Go to the Lambda console and click "Create function." Choose "Use a blueprint" and Type Lex to find the blueprint, Choose the lex book-trip-python blueprint. Choose Configure the Lambda function as follows. 
• Type a Lambda function name (trip).
• For the role, choose Create a new role from template(s) and then type a role name.
• Leave the other default values. Choose Create function

Step 5:

Test the Lambda function. You invoke the Lambda function twice, using sample data for both booking a car and booking a hotel.

Step 6:

Choose Configure test event from the Select a test event drop down. Choose Save and test Step 7:

Add the Lambda function as an initialization and validation code hook as follows:
• In Options, choose Initialization and validation code hook.
• Choose your Lambda function from the list. 
Add the Lambda function as a fulfillment code hook as follows: 
• In Fulfillment, choose AWS Lambda function. • Choose your Lambda function from the list. Choose Save.

Step 8:

Choose Build. The console sends a series of requests to Amazon Lex to save the configurations.

Step 9:

Test the bot. Now that you a have a Lambda function performing the initialization, user data validation and fulfillment, you can see the difference in the user interaction in the following conversation. Now, Click on Publish button.

COGNITO

Step 10:

Choose Manage Identity Pools. Choose Create new identity pool. Configure the identity pool. 
• Identity pool name – Enter a name that indicates the pool's purpose, such as BotPool.
• In the Unauthenticated identities section, choose Enable access to Unauthenticated identities 

Step 11:

Choose Create Pool. On the Identify the IAM roles to use with your new identity pool page, choose View Details. Record the IAM role names. You will modify them later. Choose Allow.

IAM

Step 12:

In the navigation pane, under Access Management, choose Roles. In the search box, enter the name of the authenticated IAM role and choose the checkbox next to it. Choose Attach policies. In the search box, enter AmazonLexRunBotsOnly and choose the checkbox next to it. Choose Add permissions

Step 13:

In the search box, enter the name of the unauthenticated IAM role and choose the checkbox next to it. Choose Attach policies. In the search box, enter the name of the authenticated IAM role and choose the checkbox next to it. Choose Attach policies. Now add bot name and alias name into Html code. Add identity pool Id to Html code.

S3 BUCKET

Step 14:

Go to the S3 console and click "Create bucket."

Choose a unique name for your bucket and select a region.
Leave the default settings and click "Create bucket."
Step 15:

Now click on Add folder. Add tripbot.html. Now click on upload option.

Step 16:

Choose Permissions. Under Block public access (bucket settings), choose Edit. Clear Block all public access, and choose Save changes

Step 17:

Add a Bucket policy that makes your bucket content publicly available. Select the type of policy-s3 bucket policy. Follow below steps to generate a bucket policy.

Step 18:

Select the object present in your bucket go to actions then click on the make public using ACL and then click on make public.

Step 19:

Now copy the object URL. Open the URL in a new tab.
