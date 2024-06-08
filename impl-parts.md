# Implementation Pieces

## V2

### Main Container
  - Map<ID,Room> rooms
####
  - API Endpoint(s?)
  - Game Logic

### Room
  - str ID
  - User[] users
  - Deck deck
  - Deck pile
  - int currentUserIndex

### User
  - str ID
  - Card[] hand
  ####
  - Card[] peekHand()
  - Card retrieveCard(int[] indices)
  - void addCards(Card[] cards)

### Deck
  - Card[] cards
  ####
  - Card peek()
  - Card withdraw(int count)
  - void addCards(Card[] cards)
  - void shuffle()

### Card
  - Suit suit
  - int value

### Enum Suit
  - Red
  - Yellow
  - Green
  - Blue


## V1

### Main Controller
  - Create room instance with attributes (number of players, user - player 1)
  - Add room reference to map (entry key to be public ID)
  - Control access to room (add and remove users)
  - Room existence check
  - Destroy room

### Room Management
  - Add user
  - Remove user
  - Get state
  - Entry conditions met?
  - Initialise all composite objects and start game loop
  - Is play legal? (correct player, card played allowed, integrity check...)
  - Exit conditions met?

### Room > User management
  - get current hand
  - get playable cards for current turn
  - skip turn
  - draw card
  - play card
  - get ID

### Room > Deck/slab Management
  - Create deck (combined)
  - shuffle deck
  - pop top card
  - peek at top card
  - split deck randomly or at specific place
    
### Deck > Card management
  - get value
  - get suit

### Comms
