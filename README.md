# bank_virtual_assistant
Chatbot Documentation
Chaatbot is a computer application that can initiate a conversation as well as respond to queries as human would do.
Types:
 1. Rule based engine : easy – if else- only tech people undersatnd – not user friendly
2. NLU used- common – intents of user identified and respond accordingly 

Message In: 
Interpreter :	Tries to ectract intents and entities
Tracker : Hold current state of the conversation. At what stage your chatbot at.
Policy : What actions should be taken after current state of conversation is decided by policy
Action : After identification of action , its updated into tracker. Old state of conversation is replaced by new state.  And new message sent back to user.
Message out:
Intents [nlu file] : Intention behing convesation .
Based on the input, rasa framework identifies intent.
Examples: 
nlu:
- intent: greet
  examples: |
    - hey
    - hello
    - hi
    - hello there
    - good morning
    - good evening
    - moin
    - hey there
    - let's go
    - hey dude
    - goodmorning
    - goodevening
    - good afternoon

intent: affirm
  examples: |
    - yes
    - y
    - indeed
    - of course
    - that sounds good
    - correct

intent: mood_great
  examples: |
    - perfect
    - great
    - amazing
    - feeling like a king
    - wonderful
    - I am feeling very good
    - I am great
    - I am amazing

intent: bot_challenge
  examples: |
    - are you a bot?
    - are you a human?
    - am I talking to a bot?
    - am I talking to a human?

Utterances [Domain file] : includes responses by bot.
Examples: 
utter_greet:
- text: "Hey! How are you?"

utter_did_that_help:
- text: "Did that help you?"

utter_happy:
- text: "Great, carry on!"

Stories [Stories file] : Order in which conversation is going to happen.

Example: 
story: happy path
  steps:
  - intent: greet
  - action: utter_greet
  - intent: mood_great
  - action: utter_happy

story: sad path 1
  steps:
  - intent: greet
  - action: utter_greet
  - intent: mood_unhappy
  - action: utter_cheer_up


Problem statement :

Custom intents :
Custom stories :
 Test through UI :
Deployment : 

