# Workshop-Conversational-AI : NLU using LUIS

## Workshop Abstract

In this workshop you will be creating a NLU model using LUIS. You are creating a NLU model that would work within a HR bot for Contos.com. This bot will be used by the employees of Contos.com
addressing seveler of their actions and interactions. To create this model, we have collected user utterances of employees who would like to do several functions. These functions are requesting a customized HR letter, requesting and inquirying about leves, and orchestrating and scheduling an interview and interview feedback. In this workshop you will learn how to build an NLU model, and make sense of how to handle the utterances and how to design a schema for this model You'll be introduced to the concepts of NLU, Machine Teaching and beyond 

***Technologies included:** Azure Language Understanding Cognitive Service, BotFramework, BotBuilder*

> If you are presenting this content please find [resources here](workshop-instructions-presenter.md)

## Pre-requisites

* Laptop with a modern web browser (Edge, Chrome etc)
* Access to a [Azure Subscription](https://azure.microsoft.com)
* [Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=aimlworkshop-github-amynic)
* Basic understanding of how to access code and instructions from [GitHub](https://guides.github.com/)

# Tasks
This workshop consists of 5 tasks listed below which should be followed and achieved in order to complete the workshop. 

- **Task 1**: [Creating a Basic LUIS model]
- **Task 2**: [Ading multiple domains/functionality to the model] 

# Overview of data files 
For this workshop we have collected a set of user utterances that address the three major functions required from this model. This data set includes

- [Leave Request](Data/HR_vacation_data.csv)
- [Custom HR letter](Data/HR_letter_data.csv)
- [Interview management](Data/HR_interview_data.csv)

Each file contains the utterance, the entities and their types and the labeled intents for these utterances. 

# Lets get Started ...

Follow the link to proceed to [Tasks](workshop-task.md)


# Completed the Workshop?

### Don't forget to delete your resources

#### Full Teardown instructions

* Enter the Azure Portal and delete the **Azure Resource Group** you created to remove all resources for this project


# Resources and Continued Learning

- [NLUDevOps tools](https://github.com/Microsoft/NLU.DevOps) 
- [Bot Framework Documentation](https://docs.botframework.com)
- [Bot Basics](https://docs.microsoft.com/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [Bot Framework Emulator](https://github.com/Microsoft/BotFramework-Emulator/releases) 
- [Dialogs](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-dialog?view=azure-bot-service-4.0)
- [Bot Framework Composer](https://github.com/microsoft/BotFramework-Composer)
- [Adaptive Dialogs](https://github.com/Microsoft/BotBuilder-Samples/tree/master/experimental/adaptive-dialog)
- [Gathering Input Using Prompts](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-prompts?view=azure-bot-service-4.0&tabs=csharp)
- [Activity processing](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [Azure Bot Service Introduction](https://docs.microsoft.com/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [Azure Bot Service Documentation](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)
- [.NET Core CLI tools](https://docs.microsoft.com/en-us/dotnet/core/tools/?tabs=netcore2x)
- [Azure CLI](https://docs.microsoft.com/cli/azure/?view=azure-cli-latest)
- [Azure Portal](https://portal.azure.com)
- [Language Understanding using LUIS](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/)
- [Channels and Bot Connector Service](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)


# Feedback Loop

Do you have a comment, feedback, suggestion? Currently, the best feedback loop for content changes/suggestions/feedback is to create a new issue on this GitHub repository. To get all the details about how to create an issue please refer to the [Contributing docs](../CONTRIBUTING.md)
