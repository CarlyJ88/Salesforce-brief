# Brief

## High level requirements
What should the integration do?:
- It should know which Slack channel to send the opportunity message to depending on whether they are in UK/US/EU Salesforce team
- The opportunity name, closing date, type, account name, ammount and owner need to be displayed in the correct format
- The owner will have an email address associated with them

## An overview of how the integration could work
The relevant information will be sent via a POST request where the details will be converted from one format into another which will be understood by the relevant Slack channel and shown in the correct format. The software we provide can take the relevant input and search through it until the opportunity name, closing date, type, account name, account, and owner are located and feed this information into the correct Slack channel. The file we search through will have a key letting us know which country the opportunity belongs to and we can use that to identify which channel to send the opportunity to. Our Application Programming Interface (API) has a wrapper which means we can access all methods in the Slack API so we can make the relevant calls such as channels.join as we will need to be able to join the correct channel to send the message. Also we can use chat.postMessage to send the message to the channel and use conversations.setPurpose to set the purpose of the channel i.e."Opportunity created with stage Qualification".

## Follow up questions to clarify with the customer
- Would you like the owner email to be available on the Slack message?
- Would you like the date to be formatted in a different way?
- Would you like the currency symbol to be changed depending on which Slack channel the message is sent to i.e for UK(£), EU(€), US($).