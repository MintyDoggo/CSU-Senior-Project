## Requirement #01
**Type:** Functional

**Description:** The game should extend the character movement component to add additional functionality

**Rationale:** This is fundamental to the base game movement

**Fit Criterion:** A character can use this movement component and the new features it offers

**Priority:** Essential

**Dependencies:** (none)


## Requirement #02
**Type:** Functional

**Description:** The game should allow a fixed camera stage where the user can walk around a rectangal properly

**Rationale:** This is fundamental to the base game

**Fit Criterion:** A character can walk around the map fully with the gravity changing properly

**Priority:** Essential

**Dependencies:** (none)


## Requirement #03
**Type:** Functional / Usability

**Description:** The game should allow the user to have consistent controls where walking around a wall "pre buffers" the previous input

**Rationale:** Neccesary for an intuitive experience

**Fit Criterion:** User can hold arrow direction of previous surface to walk down on other surface for a short period of time

**Priority:** High

**Dependencies:** Requirement #02 and Requirement #01


## Requirement #04
**Type:** Functional

**Description:** The game should have a destruction system where the floor is destructable and triggered by certain events

**Rationale:** Will be neccesary for implementing enemies in the game

**Fit Criterion:** Events can trigger destruction of objects.

**Priority:** Essential

**Dependencies:** Requirement #02


## Requirement #05
**Type:** Functional

**Description:** Enemies (animals) are added to the base game

**Rationale:** Fundamental to the base

**Fit Criterion:** Enemies can freely move around inside box, but only a single direction when outside the box.

**Priority:** Essential

**Dependencies:** Requirement #02


## Requirement #06
**Type:** Functional

**Description:** Enemies can break blocks from the ground

**Rationale:** Will introduce a challenge to the game where you are required to keep them in

**Fit Criterion:** Enemies can use the destruction system to break blocks when they touch them from the inside, not the outside.

**Priority:** Essential

**Dependencies:** Requirement #05 and Requirement #04


## Requirement #07
**Type:** Performance

**Description:** Enemy AI does not overload system resources

**Rationale:** Using too much of the system could cause problems especially when introducing multiplayer

**Fit Criterion:** The game should run with very little CPU usage 

**Priority:** High

**Dependencies:** Requirement #05


## Requirement #08
**Type:** Usability / Ease of Use

**Description:** Introduce game UI to start, pause, and end game.

**Rationale:** Needed for options menu and other parts of game. Helps overal intuivitness

**Fit Criterion:** UI can access all parts of game without getting trapped

**Priority:** Medium

**Dependencies:** (none)


## Requirement #09
**Type:** Personalization

**Description:** The game allows for some basic game personalization, such as graphics and controls

**Rationale:** Will help people on less performant systems and to adjust controls accordingly

**Fit Criterion:** User can easily change game options

**Priority:** Low

**Dependencies:** Requirement #08


## Requirement #10
**Type:** Functional

**Description:** Introduce jump mechanic

**Rationale:** Necessary to avoid enemies and make the game playable

**Fit Criterion:** Player can jump up and down using character movement component

**Priority:** Essential

**Dependencies:** Requirement #01


## Requirement #11
**Type:** Functional

**Description:** Allow jump mechanic around corners of stage

**Rationale:** Necessary to avoid enemies and stay on walls.

**Fit Criterion:** Player can freely jump around the corner of the stage

**Priority:** Essential

**Dependencies:** Requirement #01 and Requirement #10


## Requirement #12
**Type:** Functional

**Description:** Introduce timer for each stage

**Rationale:** Timer is needed to determine who moves onto the next stage

**Fit Criterion:** Timer runs out and game ends (for a minimum viable product)

**Priority:** High

**Dependencies:** (none)


## Requirement #13
**Type:** Functional

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 


## Requirement #14
**Type:** 

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 


## Requirement #15
**Type:** 

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 


## Requirement #16
**Type:** 

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 


## Requirement #17
**Type:** 

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 


## Requirement #18
**Type:** 

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 


## Requirement #19
**Type:** 

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 


## Requirement #20
**Type:** 

**Description:** 

**Rationale:** 

**Fit Criterion:** 

**Priority:** 

**Dependencies:** 
