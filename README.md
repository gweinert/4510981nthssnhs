##Week 4 assessment

Fork and clone, then submit a PR when you're done. Good luck!

###1. We have some queries for you:

Answer [these 10 questions](https://docs.google.com/forms/d/1pxzwnNQgksO9BOvC56F9fdogG22abKeMXMCECdq6YjU/viewform?usp=send_form) on a Google form.

###2. Now you will have some queries:

Run the 6 queries in the `mode_queries.md` file on the [Mode Analytics editor](https://modeanalytics.com/editor). Save your query in the file.

###3. Database design

A local mixed martial arts (MMA) league has asked you to redesign their web page so they can market events and sell tickets. (Right now it's just a landing page with the league's phone number: 911.)

The league holds an event about once a month at one of a handful of regular venues. Every venue has a different capacity. Every event has between 8 and 12 fights. The fights are scheduled in a certain order but they won't start at a specific time.

The league has 10 weight classes, 5 each for men and women, with a minimum weight for each. Fights have two fighters, who both belong to the same weight class. After the fight is over, there has to be a record of the winner. Fights don't end in draws.

Design the data model for this client. Use any design tools you like. Save your model as text or a legible image file.


VENUE TABLE
  -id
  -location
  -capacity
  -date
  -ticket_price

FIGHTS TABLE
  -id
  -venue_id
  -schedule_id (goes after this fight)

  =>VENUE has a many-to-one relationship with fights

SCHEDULETTABLE
  -id
  -fight_id

FIGHTERS TABLE
  -id
  -name

WEIGHT_CLASS TABLE
  -id
  -fighter_id

=> fighter has one-to-one relationship with weightclass

FIGHTS-FIGHTERS JOIN TABLE
  -id
  -fight_id
  -fighter_id
  - winner_boolean

=>a fighter has a many to many relationship with fights

