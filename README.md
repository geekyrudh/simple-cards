# simple-cards
## Ideas for a simple card game

### Rules/Mechanics
- 4 suits - red,green,blue,yellow
- 10 cards each suit, numbered
- multiple decks (randomised) in play to prevent counting
- each player starts with 'n' cards
- there is a slab of shuffled, face down cards
- the  open pile starts with a card drawn from the slab
- upto one card can be added to the pile every turn, as long as it is either:
    - Same suit as the one on top of the pile
    - same number as the one on top of the pile
- Player can always skip their turn
- if a player does not have a suitable card:
    - they can draw one card from the slab
    - play a card if they now have a suitable one
- first player to get rid of cards wins

### Process Description
- Server creates instance of room when requested with:
  - room ID
  - Number of players expected
  - First player ID
- Returns creation message and waits for people to join
- Up to 3 additional players can request to join a room by providing the room ID
- Game starts as soon as required number of people join
- On game start:
  - number of decks in play determined (randomly)
  - decks generated
  - decks shuffled
  - cards assigned to players
  - First card is added to pile
  - Server waits for input from P1
- Use WebSockets(?) to update the server and all clients on every action
- When it's a player's turn:
  - User can pass turn to next player
  - User can pick a card from slab:
    - Card count updated
    - if no legal cards in hand, automatically pass turn to next player othereise retain turn
  - they pick one card to play from the hand (UI validation as 1st line of def)
  - Server refuses played card if illegal. User retains turn.
  - if card legal:
    - Pile updated
    - Card count updated
    - Win condition checked
    - Pass turn ahead if no win
- On win:
    - send win message
    - reveal all cards