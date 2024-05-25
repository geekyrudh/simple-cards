## Implementation Pieces

### Room Management
  - Create instance with attributes (number of players, user - player 1)
  - Add reference to map (entry key to be public ID)
  - destroy room and remove references
  - Add user to room
  - Remove user from room
  - get room state
  - existence check
  - Entry conditions met?
  - initialise all composite objects and start game loop
  - is play legal? (correct player, card played allowed, integrity check...)
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
