# Versions

## Current

* Actions
  * Refactored language helper functions
* Intents & training data
  * Added internet_problem intent which starts form_troubleshoot_internet form
  * Removed Pokémon features
* Forms
  * Added form_troubleshoot_internet with its FormValidationAction and ActionAskSlotNames

## 2021.03.08

* Actions
  * Added functions (Modified Database class & language-dependent template)
  * Converting utterances into actions that utter the message corresponding to the selected language.
  * Minor code changes.
* Intents & training data
  * Working on basic customer support.
* Multilanguage support
  * Converting utterances into actions that utter the message corresponding to the selected language.

## 2021.03.01

* Actions
  * Added helper classes and functions (Database query & language-dependent utterance)
  * Minor code changes.
* Multilanguage support
  * Understands 4 languages: English, French, Arabic, Armenian.
  * Instead of utterances we should use actions that utter the message corresponding to the selected language.
  * The chatbot will reply in a select language independently of the language of the input. The user can change this language at any time.

## 2021.02.24

* Actions & training data
  * Queries database when asked about quota (using form)
  * Added "How are you?" intent
* Other
  * Added lookup table for person names

## 2021.02.20

* Upgraded for Rasa 2.3.0
  * DIET and TED confidence use now cosine distance.
  * DIET loss type is now cross_entropy (softmax is deprecated) and constrain_similarities is set to True (recommended when using cross_entropy).
* Actions & training data
  * Weather action now supports inputs without a city name and will use last city name in that case.
  * A new Out-Of-Scope intent was added with a corresponding custom action that does a Google search.
* Pipeline
  * See Rasa 2.3.0 modifications mentioned above.
  * The pipeline was changed to use SpaCy. The chatbot does a way better job at detecting city names.
  * Number of epochs was overkill. It went from 16k to 128 epochs for DIET and TED.
* Other
  * Added tensorboard support.
  * "lookup" entry in _nlu.yml_ is removed, added _data/lookups/pokemon_name.yml_ instead to let Rasa search automatically.

## 2021.02.13

* This chatbot can recognize if a given Pokemon exists and gives you the weather in a given city or country.
* Continuous Integration support, Non-Countinuous Deployment via docker push/pull.
