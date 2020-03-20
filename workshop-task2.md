# Task 2 - Adding more functionality to your model

## Summary
In this exercise you will start to expand your model by adding more domains to the NLU model you created.


## What you need
- Download the [Custom HR Letter Data Set](Data/HR_letter_data.csv)
- Login to the [LUIS Preview Portal](http://preview.luis.ai)
- Select your application, go to manage, select versions and clone the version to create a new model


# What to do

There are three main steps:
1. Add new Intents and label appropriate entities


# Considerations when adding more intent
As previously mentioned in the previous task, intents classification is based on the words that define utterances in this class. In turn when adding a new intent, you must consider
if the utterances overlap with already existing intents. If these is no overlap, you could consider adding them as separate intents immediately. 

Some points to consider:
- There is in many cases some aspects of the bot that are common, such as the intent for "confirmation" or "greeting" and the LUIS 
model is state-less. In turn if you need to distinguish between them based on the "domain", this will have to be either in the post-LUIS
processing, which retains state, or it would deem it necessary to fork out a different model and to architect a solution accordingly.
- To emphasis the distinction between the different intents, you could add the key words as dictionaries in the descriptors, and 
use them as features to your models. For example the words in the leave request would include things like "leave", "vacation", "balance" etc.. 
While the custom HR latter would use words like "salary", "starting date", "letter" and the likes. You should add them in one or more 
descriptor and link them to the models. `

Once you have defined the intents start adding them to your model on the portal


# Considerations when adding more entities
Entities include sequence labeling across all utterances. In turn you should consider the following

- Labeling has to be consistent across the application. If you have opted to select entities that so happen to be common in the 
utterances of the new domain, you need to also label them accordingly. 
- Make sure to reuse entities, or to consider generalizing their concepts to encompass both models if there are similarities.

Once you have defined the entities, start adding them to your model on the portal and use them for labeling.


## LUIS performs extraction and not resolution!
LUIS is intended to perform extraction and classification and not resolution. In turn if an utterance states "I would like to request 
a space vacation" the extraction SHOULD produce that the vacation type is "space", this is the extraction. The resolution of the entity
to a valid vacation type is the responsibility of the logic that follows the extraction.

If you opt to limit the extraction to only valid "exact match" elements, you could constrain the entity extraction using a dictionary, or
list entities, of valid terms. Mind you this hugely limits the versatility of the model and its ability to overcome mistakes in utterances.
