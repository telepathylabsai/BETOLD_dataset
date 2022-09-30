============================================================
BETOLD: A Task-Oriented Dialog Dataset for Dialog Breakdown
============================================================

.. image:: https://img.shields.io/github/license/telepathylabsai/BETOLD_dataset
   :alt: GitHub

**BETOLD** (Breakdown Expectation for Task-Oriented Long Dialogs) is a
task-oriented dialog dataset, derived from real conversations between system
and user in order to fulfill the task of booking an appointment.
The aim of the dataset is to predict **LUFHs**, i.e. **user-initiated (U) forward calls (F)
and hang-ups (H) that happen in a late (L) point of the conversation**.
This dataset is characterized by NLG and NLU intents and entities.
It does not provide any textual utterances.

This work has been accepted at the COLING 2022's
workshop `When creative AI meets conversational AI <https://sites.google.com/view/cai-workshop-2022>`_.
(Paper will be released soon)


******************
Dataset
******************

Dataset Features
==================

All dialogs include:

* LUHF: binary label 'luhf' or 'not_luhf'.
* utterances_annotations: contains all NLU and NLG intents and entities.
  * caller_name: indicates if it is a NLU (i.e a user input) or NLG (i.e a system input).
  * intent: the purpose which the speaker wants to achieve.
  * entities: slots extracted from NLU and NLG giving context to the conversation.


Structure
==================

The features are structured in the following way:

 .. code-block:: bash

  [
    {
      "LUHF": "luhf",
      "utterances_annotations": [
        {
          "caller_name": "nlg",
          "intent": "intro_assistant_1",
          "entities": [
            {
              "entity": "recording_warning"
            }
          ]
        },
        {
          "caller_name": "nlg",
          "intent": "intro_assistant_2",
          "entities": [
          ]
        },
        {
          "caller_name": "nlu",
          "intent": "schedule",
          "entities": [
          ]
        }
      ]
    }
  ]


See the file `BETOLD_description.md` and the paper (released soon!) for more details on the creation of the dataset and on the features.

******************
Team
******************

- Silvia Terragni (<silvia.terragni@telepathy.ai>)
- Bruna Guedes
- Andre Manso
- Modestas Filipavicius
- Nghia Khau
- Roland Mathis​


***********************
How to cite this work
***********************
This work has been accepted at the COLING 2022's workshop `When creative AI meets conversational AI <https://sites.google.com/view/cai-workshop-2022>`_.
If you decide to use this resource, please cite:

::

    @inproceedings{terragni2022betold,
        title={{BETOLD}: A Task-Oriented Dialog Dataset for Breakdown Detection},
        author={Terragni, Silvia and Guedes, Bruna and Manso, Andre and Filipavicius, Modestas and Khau, Nghia and Mathis​, Roland},
        year={2022},
        booktitle={Proceedings of the 2rd Workshop When Creative AI Meets Conversational AI (CAI2)",
        month = oct,
        year = "2022",
        publisher = "Association for Computational Linguistics",
        url = "",
        pages = "",
    }
