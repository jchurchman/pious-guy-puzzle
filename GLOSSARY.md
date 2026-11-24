# Pious Guy Puzzle

A real-time, tile-based puzzle game whose rules are a homage to the Chip's Challenge genre, wearing an original skin: a guy who has had a rough life, seeking answers and enlightenment. The theme is universal, echoing how hard life feels these days without pointing to any specific religion.

## Language

### The world

**Level**:
One hand-authored puzzle: a grid of Tiles with a starting position for the Guy, completed by reaching the Exit.
_Avoid_: Puzzle, stage, map, board

**Level Sequence**:
The fixed order in which Levels are played, each building on the rules introduced by the ones before it.
_Avoid_: Campaign, world, chapter

**Level Code**:
A four-letter code belonging to a Level. Completing a Level shows the next Level's code, and entering a code starts that Level from its beginning.
_Avoid_: Password, save code

**Viewport**:
The square of Tiles centered on the Guy that the Player sees clearly: 7×7 by default.
_Avoid_: Camera, screen, view

**Fog**:
The dimmed ring of Tiles drawn around the Viewport (out to 11×11), hinting at what lies beyond without revealing it.
_Avoid_: Darkness, shroud

**Tile**:
A single square of a Level's grid, holding exactly one kind of terrain or object.
_Avoid_: Cell, square, block

### Timing

**Tick**:
One fixed step of game time. Everything in a Level advances on Ticks, whether or not the Player is pressing a key.
_Avoid_: Frame, turn, step

**Timer Mode**:
A Player setting that chooses how time works in every Level: **Casual** (elapsed time counts up, no limit) or **Countdown** (each Level's Time Limit counts down).
_Avoid_: Difficulty, game mode

**Time Limit**:
The authored amount of time a Level allows in Countdown mode. Running out of it is a Death.
_Avoid_: Par, deadline

**Started**:
A Level becomes Started on the Guy's first move. Before then the Level is frozen and no time passes; once Started, the Timer Mode is locked until the Level ends or restarts.
_Avoid_: Begun, running, active

**Best Time**:
The best completion of a Level the Player has achieved in each Timer Mode: the fastest elapsed time in Casual, the most time remaining in Countdown.
_Avoid_: High score, record

### People

**Guy**:
The character the Player controls: the "pious guy".
_Avoid_: Avatar, Priest, Seeker, hero, Chip

**Player**:
The person playing the game, as distinct from the Guy they control.
_Avoid_: User, gamer

### Terrain and objects

**Key**:
A colored object the Guy picks up and spends to open a Door of the same color. Each color has its own symbol, shown on its Keys and its Doors. This is a rule name; the skin may show it as something else.

**Door**:
A colored Tile that blocks the Guy until he opens it with a matching Key, leaving floor behind. This is a rule name; the skin may show it as something else.
_Avoid_: Lock, gate

**Hazard**:
A kind of Tile that is deadly or impassable unless the Guy carries the matching Gear. Water is the first.
_Avoid_: Trap, obstacle

**Water**:
A Hazard that drowns the Guy if he enters it without Water Gear.

**Gear**:
An object the Guy picks up that makes one kind of Hazard safe for the rest of the Level. This is a rule name; the skin may show it as something else.
_Avoid_: Boots, shoes, equipment, power-up

**Water Gear**:
The Gear that lets the Guy cross Water.
_Avoid_: Flippers, boat

**Collectible**:
An object scattered through a Level; the Guy must collect every one before the Gate will open. This is a rule name; the skin may show it as something else.
_Avoid_: Chip, item, pickup

**Gate**:
A Tile that blocks the way to the Exit until every Collectible in the Level has been collected.
_Avoid_: Socket, Door, lock

**Exit**:
The Tile that completes the Level when the Guy steps onto it.
_Avoid_: Goal, finish, portal

**Hint Tile**:
A Tile that shows a short authored message while the Guy stands on it, used to teach a rule.
_Avoid_: Sign, tip, clue

**Inventory**:
The Keys (with counts) and Gear the Guy is carrying in the current Level.
_Avoid_: Items, bag

**Death**:
The Guy's failure in a Level (drowning in Water, or running out of Time Limit), which immediately restarts that Level.
_Avoid_: Game over, loss
