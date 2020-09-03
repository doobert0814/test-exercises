He's a couple mock specs to practice writing unit tests on. You should do this in the following
order

1. Write the tests, before writing any of the code for the actual classes. This will force you to
   think about the design of your classes before actually writing any code. The tests ideally are in
   order of increasing functionality, i.e. `.new` is first, then the next most basic feature next,
   etc.
2. Write your classes, implementing each feature to make each test pass sequentially before moving
   on to the next feature. If you make a test pass that breaks a previous test, go back and fix it.
   All previous tests should pass before moving on to the next one. You may have to go back and
   change either code or tests as you progress, and that's ok.

3. Once all your tests pass, you're done!

The specs given here define the public-facing methods and properties, but implementing them may
require you to add addition fields or methods not explicitly specified in the spec.

# Spec 1 - Embr

Lets build a dating app. Lets assume we have 1 user who's the batchellor, and a set of profiles of
all potential bachelorettes. If the batchellors approves of the bachelorette, they instantly match.
Like Tinder, but you match with everyone. If only.

## App Class

- []`App.new` 
    -creates a new app with preloaded list of profiles
- []`App#next_profile()` 
    - sets the next available profile as the current one, prints out
      details to the console
- []`App.current_profile` 
    -the current profile on display
- []`App#match()` 
    - matches the user with the current profile
- []`App#reject()` 
    - rejects the current profile
- []`App.matches` 
    - all profiles the user has matched with

## Profile Class

- `Profile.name` - the candidate's name
- `Profile.eye_color` - the candidates's eye color
- `Profile.age` - the candidates's age
- `Profile.occupation` - the candidates's occupation
- `Profile.hobbies` - a list of the candidates's hobbies, as a string i.e. ["eating", "hiking"]

# Spec 2 - Blackjack

We want to create a class that represents an instance of a simplified blackjack game. We'll exclude
aces and face cards for simplicity's sake.

## Hand Class

- `Hand.new` - creates a new hand
- `Hand.value` - property, current value of the hand
- `Hand.hit()` - function, deals a new random card, with value between 2-10, and adds it to
  `Hand.value`
- `Hand.is_bust` - property, true if the value of the hand is over 21
- `Hand.owner` - property, either "Player" or "Dealer"

## Game Class

- `Game.new` - creates a new game with two players - Player and Dealer
- `Game.start()` - function, starts the game, dealing two cards to each player
- `Game.current_turn` - property, either "Player" or "Dealer"
- `Game.hit()` - function, deal a card to either `Player` or `Dealer`'s hand, based on the value of
  `current_turn`
- `Game.stay()` - function, stops dealing cards to either `Player` or `Dealer`, based on the value
  of `current_turn`
- `Game.is_won` - property, true if either player or dealer busts, or both have stayed.

# Spec 3 - NeoKitties

Lets make a game where a user can create, take care of, and breed cats. Users can create 1 new cat
every 24 hours, otherwise we throw an error. Cats need to be fed once per week, or they die. Two
cats can be bred and produce a new cat, with a random mix of the parent cat's traits. Cats can only
be bred once per week and have to be at least two weeks old in order to breed.

# Kitty

- `Kitty.new` - creates a new kitty if one has not been created in the last 24hrs, otherwise throws
  an error.
- `Kitty.color` - color of the kitty.
- `Kitty.coat` - coat style of the kitty, one of tabby, solid, tortoise, colorpoint, tricolor,
  bicolor.
- `Kitty.catch_phase` - cat's signature catch phrase.
- `Kitty.age` - age of the cat, in days. hint: this field can be derived from another field, not
  explicitly included in the spec but you should consider including.
- `Kitty.is_alive` - true if the kitty has been fed in the last week.
- `Kitty.breed(other_cat)`- function, breeds Kitty with `other_cat` under the right conditions,
  otherwise throws an error.
- `Kitty.feed()` - function, feed the kitty. Throws an error if the kitty is dead.
- `Kitty.talk()` - function, says the kitty's catch phrase. Throws an error if the kitty is dead.
#test-exercises
