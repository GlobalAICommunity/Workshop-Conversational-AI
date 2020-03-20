# Task 1 - Creating a Basic LUIS model

## Summary
In this exercise you will build a basic model using the Language Understanding Cognitive Service to create a NLU model.


## What you need
- Download the [Leave Request Data Set](Data/HR_vacation_data.csv)
- login to the [LUIS Preview Portal](http://preview.luis.ai)
- Create a new application in LUIS


# What to do

There are three main steps:
1. Create a new Intent
2. labeling and creating Entities
3. Improving your model


# Create a new Intent
Intents (and their respective domains) are detected using classification. Classification assumes that you have a set of utterances that are labeled to be part of a domain/class pair. As its name implies, user intent tells us what a user is “looking to do/looking for” 
when providing an utterance. In case of basic models, intents are represented to be action verbs E.g. greeting, confirmation, request a vacation, cancel a vacation etc..

Please consider that intent take into consideration the words used in the utterance, and intent selection should be driven by this fact. In turn if utterances are clearly distinct in themselves you should model your intents to be the main driver of the model. For example having intents for requesting a leave and asking about public holidays are clearly distinct ("I want to request a paid leave for 3 days next Monday" and "What are the public holidays in France"), while creating two intents one for requesting a paid leave and one for requesting a 
sick leave is not a great idea ("I want to request a paid leave for 3 days next Monday" vs "i want to request a sick leave for 3 days next Monday").

If intents can’t have a “unique set of words” that define it then it would be ambiguous, and you should reconsider merging these intents and using entities to discriminate them.

Clearly separable intents make for good classification/detection


What would be the intents you have for the Leave request data?

Once you have defined the intents start adding them to your model on the portal

### You could use the APIs to create intents as defined in the [Documentation](https://westeurope.dev.cognitive.microsoft.com/docs/services/luis-programmatic-apis-v3-0-preview/operations/5890b47c39e2bb052c5b9c2f) 

### Make sure to check the utterances, these are cowd sourced and you need to treat them in this regard. The process of Machine Teaching also entails more consideration for the utterances through the teacher (you) as they come to be added to the model

# Create entity extractors
Entities extraction performs sequence tagging estimation. Given a collection of tagged word sequences, you would like to estimate the tags of a new utterance. User Entities are items or elements the user is taking action about. 
In case of basic models, entities are elements of intents that the bot requires to collect and are usually nouns e.g. date, type of leave, country, name etc..

Entities are divided into common entities/pre-trained and custom entities
- Common entities require no learning/training: These include pre-defined entities, and regular expressions
- Custom entities require training and are fundamental to defining the user request. Custom entities could be standalone leaf machine learnt entities, or placed in a structure or hierarchy. 

Entity hierarchies allow grouping of entities within a shared parent, such as leave details could be defined as

{LeaveType} from {DateRange:{DateStart} to {DateEnd}}

it is worth noting that the parent and children are independent, and entities could be nested in general.


You will need to create the entities and label them in the utterances. What would the entities be for the leave request data.

Once you have defined the entities, start adding them to your model on the portal and use them for labeling.

### You could use the APIs to create intents as defined in the [Documentation](https://westeurope.dev.cognitive.microsoft.com/docs/services/luis-programmatic-apis-v3-0-preview/operations/5890b47c39e2bb052c5b9c2f) 

### Make sure to check the utterances, these are cowd sourced and you need to treat them in this regard. The process of Machine Teaching also entails more consideration for the utterances through the teacher (you) as they come to be added to the model


## Actionable entities (int-ent-ities)


You could create actional entities, sometimes referred to as int-ent-ities. This entails that you label an action as an entity, either o its own or s an action within the hierarchy. This form or modeling is suitable for complicated utterances that have multiple actions embedded
within one statement. Also in the case you have very similar utterances for the same intents, and you want to use these int-ent-ities to distinguish between them. It is worth noting that you will then consume to output of LUIS as intent:entity combinations to map to your corresponding actions in the dialogue.


# Improving the model

## Verify your utterances cover appropriate variations
- Make sure words are present in the variety of their used synonyms. Make sure utterances such as “Request a vacation”, “Place a vacation”, “vacation request” etc.. all exist
- In bots people sometime use sentences that are not necessarily making grammatic sense, if utterances used follow this trend add them with the right labels. Make sure to capture different forms of utterances users say, including slang and different ways users express their request
- Add utterances which have only the entities marked up. For example, in a food ordering app, your user may just say 'Pizza' instead of 'I would like some Pizza’. Users would expect the same behavior. 
- If you have many entities structured together make sure the different manner which they are ordered are captured. “I would like to order a large extra cheese pepperoni pizza” and “extra cheese large pepperoni pizza”
- Make sure prepositions are well varied in your data

## Entity only utterances

Conversations are multi-turn and sometimes could be addressing a very specific entity request. E.g. in a flow you could find the user addressing the question, “what is the type of vacation you are requesting?”. To allow for such cases to trigger post-LUIS actions, you will have to add an utterance with only the entity and no other words. You would have to mark up the entity though.

## Handling Negation
So what happens when you want to say "Show me holidays in January" vs "don’t show me holidays in January". You could define two intents, but this would be ambiguous, and in turn you are better to define this negative aspect as an entity and capture it accordingly in your logic. 

## Considerations when using Speech
Use utterances as produced from Speech-To-Text (STT) in labeling, making sure utterances span the errors produced by the STT. Also be aware that the STT may produce recognitions that are divided/structured as separate words E.g. 756 -> seven five six. For this you should model such entities as hierarchies of smaller elements as presented.


## Model as a Feature
Model-as-a-feature enables you to use well recognized “IS-A” relationship as means to improve extraction. This happens by injecting these extractions as features to other entity extractors, or intent classifications to improve the performance. You should use these to these entities or descriptors are clear indication of the subsequent model.

### You could use the APIs to create intents as defined in the [Documentation](https://westeurope.dev.cognitive.microsoft.com/docs/services/luis-programmatic-apis-v3-0-preview/operations/5890b47c39e2bb052c5b9c2f) 
