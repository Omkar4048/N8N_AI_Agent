# N8N_AI_Agent
AI Agent Creation

To start with our new AI Agent project, we are going to use N8N software to build our first telegram AI Agent which will automate simple day to day work. First we will create project on N8N protal as shown below:
![image](https://github.com/user-attachments/assets/0605d09a-37b2-4d70-a3b3-2ba1810e3e9d)

Click on create workflow to get workspace where we can play.
![image](https://github.com/user-attachments/assets/748d896c-1088-449b-87e8-6308072edf1e)

Click on add first step, we will get multiple triggers like manual, on schedule, on app event, etc.
We will click on telegram trigger with On Message field. we will get console where we can pass connection string and we can watch output in other panel.
![image](https://github.com/user-attachments/assets/d21be172-e7cd-4da1-bfab-c03ada10218c)

Follow below link to setup telegram authentication with n8n 
https://docs.n8n.io/integrations/builtin/credentials/telegram/#related-resources

click on botfather link to create bot account on telegram. and enter below commands to get bot credentials as shown below.
![image](https://github.com/user-attachments/assets/e67fd424-0b5a-4809-92a3-ef94fb2fe0c4)

In n8n window, click on create telegram account and enter Access token and hit save.
![image](https://github.com/user-attachments/assets/2834e571-f29f-4b29-8068-1fad4a903b07)
click on "test step" and enter message in telegram bot. It will reflect message data to your telegram trigger.
![image](https://github.com/user-attachments/assets/2f7707ca-322f-4241-a319-1d7121bdcd75)

Congratulations!!! You have set up your first step successfully. We have message trigger as shown above.

Now we will create second step to record input given by user and work on the data to respond. First we will create switch to segregate Text and Voice Inputs.
Click on "+" sign next to telegram trigger. Search for Switch and enter required parameters as shown below.
![image](https://github.com/user-attachments/assets/d892768c-1d6f-4f33-a52e-54d928ed1926)

Drag Text variable from Input pane to parameters input. We can test all this setup at each step to check data flow through out model.
Similarly, we will setup second input as voice using Add Routing rule.
![image](https://github.com/user-attachments/assets/3ee7a9b2-ab99-4db6-9532-a620380550c0)
![image](https://github.com/user-attachments/assets/820797a6-5dc7-4d44-bd70-d83ddb64ac47)

Next we will pass text data to Edit Fields.
![image](https://github.com/user-attachments/assets/a942ef7b-647b-4dbf-bb1b-1e4b168f636e)
![image](https://github.com/user-attachments/assets/9f256aa5-b035-4a21-b413-54ef95447dea)
Add required parameters as shown in image to setup Edit Field.
Now, We will setup Step which will locate for Voice file in Telegram and convert it to text.
Add Step as Get File from Telegram module. and we need to pass voice message using bot to locate file location to setup.
![image](https://github.com/user-attachments/assets/fe0bd2c2-f99e-4a45-b530-c6b3bb9399ff)
We will pass voice input in parametrs section to work on that later. Don't forgot to test steps at each interval to ensure rightness.
Click on "+" to pass output of this voice to transcribe to text.
Search for OpenAI and then Transcribe a recording.

We needs to create new OpenAI account to use for this testing. 
Go to platform.openai.com and create new api keys.
Copy latest Key and enter in n8n console to test openai connectivity as shown below. 
![image](https://github.com/user-attachments/assets/186cde07-e232-40b1-8458-bc6f892cbbef)
This OpenAI module will automatically translate all your voice messages to text to use further. Now we have two inputs with same type as text.
![image](https://github.com/user-attachments/assets/44f80741-6a3b-462b-90a0-76ef78fad84b)

Create new step as "AI agent". Pass both Output to Input of newly created Agent block.
![image](https://github.com/user-attachments/assets/ced3bed4-1062-4ea8-b432-49ac822ab30a)
As shown above, we have to pass different inputs to module like Chat Model, Memory and Tool.
We have lots of Language modules like Azure OpenAI Chat Model, Google Gemini Chat Model and so on. We are gonna use Anthropic for this testing. Click on add model search for Anthropic and pass required details as shown below.
We needs to create and connect New Anthropic account on 'console.anthropic.com' using API key and select latest model from dropdown menu.
![image](https://github.com/user-attachments/assets/03afcc12-ed21-4a5a-93ed-bc48d212e606)
![image](https://github.com/user-attachments/assets/4b9c8ea5-d15a-401d-861a-4a4f6ecb9803)

Now as we have setup model to use for our AI Model. Let's setup output first to check how our model performs for both text and voice inputs. Then we will setup memory and tools which are required to make our AI module more robust.

For this demo we going to add telegram block to reply on same chat with some output for users input. The output will be in text format.
Click on Telegram and Send message and pass requried parameters as shown below.
To pass chat id, we first needs to setup AI Agent prompt source. click on AI Agent, and setup prompt source as Define belwo and pass OpenAI text field as input.
Also, add system message to test from options.
![image](https://github.com/user-attachments/assets/02d0df14-b01b-4a29-b4f9-8789d8387170)
Now test the step with some input prompt and you will see output in model output section. Let's complete final step to connect telegram with model to reply on message sent by user on Bot.
Pass switch chat id to id and text as output of AI model.
![image](https://github.com/user-attachments/assets/9a312a24-b040-48a7-81ba-a7b52095483b)

Boom!!! We have successfully created bot which revert to user query using AI. Test the workflow by passing inputs to Bot and we will get some output as shown below.
![image](https://github.com/user-attachments/assets/fb1094db-4b17-4ea1-ada4-bec0c82a57f5)
