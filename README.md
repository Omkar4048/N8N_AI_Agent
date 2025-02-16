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
In n8n window, click on create telegram accound and enter Access token and hit save.
![image](https://github.com/user-attachments/assets/2834e571-f29f-4b29-8068-1fad4a903b07)
click on test step and enter message in telegram bot. It will reflect message data to your telegram trigger.
![image](https://github.com/user-attachments/assets/2f7707ca-322f-4241-a319-1d7121bdcd75)

Congratulations!!! You have set up your first step successfully. We have message trigger as shown above.

