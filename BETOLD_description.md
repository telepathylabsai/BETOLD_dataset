# Dataset

### Overview
Breakdown Expectation for Task-Oriented Long Dialogs (BETOLD) is a
Privacy-Preserving dataset, derived from real conversations between system
and user in order to fulfill the task of booking an appointment.
This dataset was anonymized, by removing text or any natural language derived
from utterances.

This dataset is made of long dialogs of at least 8 turns, in which each turn
is defined by the change in speaker. The aim of the dataset is to predict
user-initiated (U) forward calls (F) and hang-ups (H) that happen in a late
(L) point of the conversation. Therefore all conversations are labeled either
as LUHF or non-LUHF.

### Numbers
This dataset contains 13,524 conversations, with a ratio of successful
calls/LUHFs of 2:1.
The resulting dataset contains 4,508 LUHFs and 9,016 non-LUHFs.

- min number of turns per dialog: 8
- mean number of turns per dialog: 10.42
- median number of turns per dialog: 10.0
- max number of turns per dialog: 34

### Dataset Features
All dialogs include:
- LUHF: binary label 'luhf' or 'not_luhf'.
- utterances_annotations: contains all NLU and NLG intents and entities.
    - caller_name: indicates if it is a NLU (i.e a user input) or NLG (i.e a system input).
    - intent: the purpose which the speaker wants to achieve.
    - entities: slots extracted from NLU and NLG giving context to the conversation.

### Structure
The features are structured in the following way:

```bash
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
```

### List of possible entities

| Type | Entity | Description
| :---  | :---  | :---     
|NLG     |     alternative_date_proposal     |     date of alternative time for appointment     |     
|NLG     |     ask_means_of_transportation     |     means of transportation proposed     |     
|NLG     |     ask_to_schedule     |     confirmation of next steps of scheduling appointment     |     
|NLG     |     available_slot_to_schedule     |     time of slot available for scheduling appointment     |     
|NLG     |     closing_hours     |     closing hours of given store     |     
|NLG     |     date_proposal     |     date proposed     |     
|NLG     |     device_make     |     brand of cellphone     |     
|NLG     |     device_model     |     model of cellphone     |     
|NLG     |     device_year     |     year of fabrication of cellphone     |     
|NLG     |     exception_days     |     days with different working hours     |     
|NLG     |     location_store     |     address of a given store     |     
|NLG     |     mention_means_of_transportation     |     means of transportation chosen     |     
|NLG     |     no_slots_available     |     no options of slots for scheduling appointment are available     |     
|NLG     |     opening_days     |     opening days of week     |     
|NLG     |     opening_hours     |     opening hours      |     
|NLG     |     recording_warning     |     warning this message might be recorded     |     
|NLG     |     schedule_time     |     specific time indication for scheduling appointment     |     
|NLG     |     services_closing_hours     |     closing hours of given service     |     
|NLG     |     transportation_type_selection     |     transportation type selected     |     
|NLG     |     unavailable_transportation_type     |     transportation type is not supported      |     
|NLG     |     user_phone_suffix     |     suffix of user's phone number     |     
|NLG     |     user_request_start_time     |     starting time for scheduling appointment     |     
|NLU     |     brand_device     |     specific brand of cellphone     |     
|NLU     |     client_name     |     name of user     |     
|NLU     |     language     |     language preference specification     |     
|NLU     |     model_device     |     speficific model of cellphone     |     
|NLU     |     numeric     |     numbers, that might be for instance the percentage of battery health     |     
|NLU     |     phone_number     |     phone number      |     
|NLU     |     sector     |     specific department of company     |     
|NLU     |     time_indication     |     specific time indication      |     
|NLU     |     time_range_indication     |     range of time preferred     |     
|NLU     |     transportation_type     |     type of transportation of cellphone, can be pick up, dropoff or waiting for service     |     
|NLU     |     type_of_repair     |     type of repair service required     |     
|NLU     |     year     |     year      |     



### List of possible intents

| Type | Intent | Description
| :---  | :---  | :---     
|NLG     |     ask_additional_service     |     ask if other services were required     |     
|NLG     |     ask_corrected_date     |     confirm if date should be corrected     |     
|NLG     |     ask_desired_service     |     ask to specify service  of cellphone     |     
|NLG     |     ask_device_brand     |     ask to specify brand of cellphone     |     
|NLG     |     ask_device_brand_model     |     ask to specify brand and model of cellphone     |     
|NLG     |     ask_device_brand_model_year     |     ask to specify brand, model and year  of cellphone     |     
|NLG     |     ask_device_model     |     ask to specify model of cellphone     |     
|NLG     |     ask_device_year     |     ask to specify year of cellphone     |     
|NLG     |     ask_device_year_brand     |     ask to specify year and brand of cellphone     |     
|NLG     |     ask_device_year_model     |     ask to specify year and model of cellphone     |     
|NLG     |     ask_first_name     |     ask user's first name     |     
|NLG     |     ask_for_battery_health     |     ask battery health from cellphone     |     
|NLG     |     ask_if_current_client     |     ask if user is a current client     |     
|NLG     |     ask_last_name     |     ask user's last name     |     
|NLG     |     ask_phone_number     |     ask user's phone number     |     
|NLG     |     ask_time_preference     |     ask user if there is a time preference     |     
|NLG     |     asked_date_too_far     |     tell user date chosen is too far in the future     |     
|NLG     |     confirm_cancel_schedule_new     |     confirm cancelation of appointment and ask new date     |     
|NLG     |     confirm_canceled_appointment     |     confirm appointment was successfully canceled      |     
|NLG     |     confirm_change_schedule     |     confirm change in date of appointment     |     
|NLG     |     confirm_date_scheduled     |     confirm date of appointment     |     
|NLG     |     confirm_phone_number     |     confirm user's phone number     |     
|NLG     |     date_schedule_no_longer_exists     |     date proposed is no longer available     |     
|NLG     |     did_not_understand     |     system does not understand user     |     
|NLG     |     disambiguate_user_profile     |     disambiguate profile in case of multiple profiles linked to one phone number     |     
|NLG     |     fail_retrieve_user_info     |     unable to find user's profile     |     
|NLG     |     failed_schedule_warning     |     system failure to schedule an appointment      |     
|NLG     |     faq_close_time     |     inform closing hours     |     
|NLG     |     faq_open_time     |     inform opening hours     |     
|NLG     |     faq_operating_hours     |     inform range of day in which service is open     |     
|NLG     |     further_requests     |     ask if there are any further requests     |     
|NLG     |     inform_schedule_inspection     |     system is finding possible slots for appointments     |     
|NLG     |     intro_assistant_1     |     introductory message presentation     |     
|NLG     |     intro_assistant_2     |     give options of possible services     |     
|NLG     |     new_user_profile_brand_model_year     |     create profile for new user     |     
|NLG     |     no_dates_available     |     no dates available for making appointments     |     
|NLG     |     no_dates_available_try_new_transportation_type     |     no dates available for making appointments with this transportation type     |     
|NLG     |     no_more_schedule_appointments     |     do not recognize the given date as an existing appointment     |     
|NLG     |     no_pre_existing_schedule     |     no appointments pre-scheduled.     |     
|NLG     |     offer_to_schedule     |     ask if user wants to schedule an appointment     |     
|NLG     |     operating_hour_and_ask_for_schedule     |     specify possible ranges of time to schedule appointment     |     
|NLG     |     propose_date     |     propose date for appointment     |     
|NLG     |     propose_earliest_time     |     propose earliest possible time for scheduling appointment     |     
|NLG     |     propose_other_transportation_of_device     |     propose other type of transportation such as waiting for the service or leaving phone     |     
|NLG     |     reconfirm_date_scheduled     |     reconfirm time of appointment scheduled     |     
|NLG     |     retrieve_user_information     |     ask phone number to find user profile     |     
|NLG     |     schedule_or_cancel     |     ask again type of service required     |     
|NLG     |     silence     |     wait in silence     |     
|NLG     |     time_asked_unavailable_propose_new     |     proposed date is unavailable, propose a new option     |     
|NLG     |     transportation_of_device     |     ask if user will wait suring service, dropoff phone or request pick up service     |     
|NLG     |     transportation_type_unavailable     |     transportation type such as waiting for the service of leaving phone is not available     |     
|NLG     |     working_on_previous_request     |     still processing previous request     |     
|NLU     |     ask_for_transportation_types     |     ask possible options of transportation of cellphone to be serviced     |     
|NLU     |     cancel     |     cancel existing appointment      |     
|NLU     |     confirm     |     agree     |     
|NLU     |     inconclusive     |     uncertainty in statement     |     
|NLU     |     inform     |     inform      |     
|NLU     |     negate     |     disagree     |     
|NLU     |     noise     |     noise in user's side of conversation     |     
|NLU     |     other     |     other cases     |     
|NLU     |     rephrase     |     ask to repeat question     |     
|NLU     |     reschedule     |     ask to reschedule appointment     |     
|NLU     |     salutation     |     greeting     |     
|NLU     |     schedule     |     ask to schedule an appointment     |     
|NLU     |     transfer_agent     |     ask to trasnfer to a human agent     |     
|NLU     |     unregistered_user     |     user is not yet registered in the database     |     
|NLU     |     urgency     |     indicate it is an urgent situation     |     
|NLU     |     user_initial_request     |     indication of goal of the call     |     
|NLU     |     user_proposed_date     |     propose a specific date for appointment     |         


###  Collection Methodology
This dataset was extracted from real conversations between June 11 and August 29 of 2022.
