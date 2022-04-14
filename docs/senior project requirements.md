## Requirement #01
**Type:** Functional

**Description:** The game should extend the character movement component to add additional functionality

**Rationale:** This is fundamental to the base game movement

**Fit Criterion:** A character can use this movement component and the new features it offers

**Priority:** Essential

**Dependencies:** (none)


## Requirement #02
**Type:** Functional

**Description:** The game should allow a fixed camera stage where the user can walk around a rectangle properly

**Rationale:** This is fundamental to the base game

**Fit Criterion:** A character can walk around the map fully with the gravity changing properly

**Priority:** Essential

**Dependencies:** (none)


## Requirement #03
**Type:** Functional / Usability

**Description:** The game should allow the user to have consistent controls where walking around a wall "pre buffers" the previous input

**Rationale:** Necessary for an intuitive experience

**Fit Criterion:** User can hold arrow direction of the previous surface to walk down on another surface for a short period of time

**Priority:** High

**Dependencies:** Requirement #02 and Requirement #01


## Requirement #04
**Type:** Functional

**Description:** The game should have a destruction system where the floor is destructible and triggered by certain events

**Rationale:** It will be necessary for implementing enemies in the game

**Fit Criterion:** Events can trigger the destruction of objects.

**Priority:** Essential

**Dependencies:** Requirement #02


## Requirement #05
**Type:** Functional

**Description:** Enemies (animals) are added to the base game

**Rationale:** Fundamental to the base

**Fit Criterion:** Enemies can freely move around inside the box, but only in a single direction when outside the box.

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

**Rationale:** Using too much of the system could cause problems, especially when introducing multiplayer

**Fit Criterion:** The game should run with very little CPU usage 

**Priority:** High

**Dependencies:** Requirement #05


## Requirement #08
**Type:** Usability / Ease of Use

**Description:** Introduce game UI to start, pause, and end game.

**Rationale:** Needed for options menu and other parts of the game. Helps overall intuitiveness

**Fit Criterion:** UI can access all parts of the game without getting trapped

**Priority:** Medium

**Dependencies:** (none)


## Requirement #09
**Type:** Personalization

**Description:** The game allows for some basic game personalization, such as graphics and controls

**Rationale:** Will help people on less performant systems and adjust controls accordingly

**Fit Criterion:** Users can easily change game options

**Priority:** Low

**Dependencies:** Requirement #08


## Requirement #10
**Type:** Functional

**Description:** Introduce jump mechanic

**Rationale:** Necessary to avoid enemies and make the game playable

**Fit Criterion:** Player can jump up and down using the character movement component

**Priority:** Essential

**Dependencies:** Requirement #01


## Requirement #11
**Type:** Functional

**Description:** Allow jump mechanic around corners of the stage

**Rationale:** Necessary to avoid enemies and stay on walls.

**Fit Criterion:** Player can freely jump around the corner of the stage

**Priority:** Essential

**Dependencies:** Requirement #01 and Requirement #10


## Requirement #12
**Type:** Functional

**Description:** Introduce timer for each stage

**Rationale:** Timer is needed to determine who moves onto the next stage

**Fit Criterion:** Timer runs out and the game ends (for a minimum viable product)

**Priority:** High

**Dependencies:** (none)


## Requirement #13
**Type:** Functional

**Description:** Introduce a dedicated server

**Rationale:** Required for the multiplayer side of the game to work

**Fit Criterion:** The game should use a dedicated server to manage up to 40 clients

**Priority:** Essential

**Dependencies:** Requirement #01 and Requirement #10


## Requirement #14
**Type:** Performance / Robustness or Fault-Tolerance

**Description:** Make character and enemy components with client-side prediction

**Rationale:** Will be necessary for making the multiplayer work effectively

**Fit Criterion:** Server can manage up to 40 clients

**Priority:** High

**Dependencies:** Requirement #13


## Requirement #15
**Type:** Functional

**Description:** Make event on the server for losing life

**Rationale:** In order to control the online aspect of the game, we need to have a way to track which players are dead and alive

**Fit Criterion:** Getting hit by an enemy should cause you to lose the game

**Priority:** Essential

**Dependencies:** Requirement #12


## Requirement #16
**Type:** Security

**Description:** Create a dedicated server using a reliable company

**Rationale:** Compromised servers can cause future complications

**Fit Criterion:** Server should be trustworthy with a good reputation to avoid user data leaks

**Priority:** High

**Dependencies:** Requirement #13


## Requirement #17
**Type:** Scalability or Extensibility

**Description:** Separate all movement functionality

**Rationale:** Allows different movement functionality for different stages and future development

**Fit Criterion:** The character movement component can be fit into any game

**Priority:** Medium

**Dependencies:** Requirement #02 and Requirement #01


## Requirement #18
**Type:** Functional

**Description:** Create general game loop

**Rationale:** Necessary for entire game to function as one thing

**Fit Criterion:** After each level, it progresses to the next until there is one player left. Once he wins, everyone is returned to the menu

**Priority:** High

**Dependencies:** Requirement #13


## Requirement #19
**Type:** Look and Feel / Appearance

**Description:** Implement cel shader

**Rationale:** Important for turning a 3D game into an easy to comprehend side scroller game.

**Fit Criterion:** Cel shader works on characters as well as environments.

**Priority:** low

**Dependencies:** (none)


## Requirement #20
**Type:** Look and Feel / Style

**Description:** Replace all temporary meshes and models with consistently themed assets

**Rationale:** Needed to style the game accordingly

**Fit Criterion:** All assets are redone with proper game assets

**Priority:** low

**Dependencies:** Requirement #19
