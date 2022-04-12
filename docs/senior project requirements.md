Requirement #01
===============

**Type:** 
Functional

**Description:** 
The module should keep a record of past game states.

**Rationale:** 
This is an essential component of rollback netcode.

**Fit Criterion:** 
The module can keep track of at least 20 frames of past game states.

**Priority:** 
Essential

**Dependencies:** 
(none)

Requirement #02
===============

**Type:** 
Performance / Speed and Latency

**Description:** 
The module should have adequate performance when keeping a record of game state
data.

**Rationale:** 
If the process of saving game state data slows down the game performance, then
the benefits of rollback are lost.

**Fit Criterion:** 
Test projects with reasonable complexity are not slowed down when the module is
active.

**Priority:** 
Essential

**Dependencies:** 
Requirement #01

Requirement #03
===============

**Type:** 
Capacity

**Description:** 
The user should be able to specify the amount of past frames kept, up to five
seconds' worth.

**Rationale:** 
The ability to keep track of past game states may be useful for more than just
rollback netcode, so Essential settings for this may be useful. Lower settings
may also help improve performance on weak hardware.

**Fit Criterion:** 
The module has a setting to save variable amounts of game state data, up to
300 ticks (five seconds in many games).

**Priority:** 
High

**Dependencies:** 
Requirement #01

Requirement #04
===============

**Type:** 
Functional

**Description:** 
The module's past game state data should be exposed to the user.

**Rationale:** 
Accessing past game state data may be useful for certain game mechanics, such
as rewinding to the recent past in a time travel game.

**Fit Criterion:** 
The module has a function to retrieve data on a game object from a specified
amount of time in the past.

**Priority:** 
High

**Dependencies:** 
Requirement #01

Requirement #05
===============

**Type:** 
Functional

**Description:** 
The module should have functionality to roll back and resimulate the game state
according to the conventions of rollback.

**Rationale:** 
This is an essential component of rollback netcode.

**Fit Criterion:** 
The module emits different [signals](https://docs.godotengine.org/en/latest/getting_started/step_by_step/signals.html) for rolling back time and resimulating game
ticks; when rolling back, it also automatically handles the restoration of the
tracked game state data.

**Priority:** 
Essential

**Dependencies:** 
Requirement #01

Requirement #06
===============

**Type:** 
Performance / Speed and Latency

**Description:** 
The process of rolling back the game state should have acceptable performance.

**Rationale:** 
If this has poor performance, the benefits of rollback are lost.

**Fit Criterion:** 
Rolling back to a previous frame does not cause game lag in a reasonable test
project.

**Priority:** 
Essential

**Dependencies:** 
Requirement #05

Requirement #07
===============

**Type:** 
Functional

**Description:** 
The module should include networking capabilities to enable online multiplayer
between two clients.

**Rationale:** 
This is an essential component of rollback netcode.

**Fit Criterion:** 
The module can connect to another client running the same software and exchange
packets containing input data using Godot's built-in network features.

**Priority:** 
Essential

**Dependencies:** 
Requirement #01, Requirement #05, Requirement #17

Requirement #08
===============

**Type:** 
Usability / Learning

**Description:** 
The module should be intuitive and user-friendly.

**Rationale:** 
If the module is difficult for existing Godot users to make use of, it will be
detrimental to the goals of the project.

**Fit Criterion:** 
The module's exposed, user-facing functions follow the [Godot style guide](https://docs.godotengine.org/en/stable/getting_started/scripting/gdscript/gdscript_styleguide.html) and
are generally intuitive to use for existing Godot users.

**Priority:** 
High

**Dependencies:** 
Requirements #01-07

Requirement #09
===============

**Type:** 
Performance / Precision or Accuracy

**Description:** 
The module should be able to handle floating point errors across different
hardware.

**Rationale:** 
Due to differences in how floating point numbers are calculated on different
types of computer, keeping them in check is essential for functioning
netcode. Otherwise, the game state could drift out of sync.

**Fit Criterion:** 
If necessary, the module provides functionality to round floating point numbers
every frame, or to sync values between the two clients to correct minor
rounding errors. Research will be needed to determine which is better, or if
either is necessary at all.

**Priority:** 
High

**Dependencies:** 
Requirement #07

Requirement #10
===============

**Type:** 
Release

**Description:** 
The module should be released as an open-source project.

**Rationale:** 
This way, users can add the module to their projects and modify it for specific
use cases.

**Fit Criterion:** 
The module is released on GitHub.

**Priority:** 
High

**Dependencies:** 
The completion of the project

Requirement #11
===============

**Type:** 
Security / Privacy

**Description:** 
The module should not expose users to data leaks.

**Rationale:** 
Leaking personal information is bad.

**Fit Criterion:** 
The module cannot be exploited to retrieve any non-game-related data from
another player during network play.

**Priority:** 
High

**Dependencies:** 
Requirement #07

Requirement #12
===============

**Type:** 
Performance / Robustness or Fault-Tolerance

**Description:** 
The module should be able to handle cases where the other player loses
connection in network play.

**Rationale:** 
It's not uncommon for players to suddenly disconnect during an online game;
having a predictable way to handle this will be vital.

**Fit Criterion:** 
The module is able to detect when the other player takes too long to send a
packet, and then stop the online session. It also emits a signal when the other
player times out so that the game developer can handle it.

**Priority:** 
High

**Dependencies:** 
Requirement #07

Requirement #13
===============

**Type:** 
Usability / Personalization

**Description:** 
The module's functionality should be clearly documented.

**Rationale:** 
The easier it is to understand how to use the module, the better.

**Fit Criterion:** 
Clear documentation is included regarding how to use the module in a game. The
module's source code is clearly explained using comments.

**Priority:** 
High

**Dependencies:** 
The completion of the project

Requirement #14
===============

**Type:** 
Functional

**Description:** 
The module should be able to retrieve the latency of the current network
connection.

**Rationale:** 
Ping information is very useful in online games; it can warn players about
a bad connection, for example, prompting them to perhaps find a different
opponent.

**Fit Criterion:** 
The module has an exposed function which returns the ping time of the current
network connection.

**Priority:** 
Medium

**Dependencies:** 
Requirement #07

Requirement #15
===============

**Type:** 
Functional

**Description:** 
The module should provide a way to communicate miscellaneous information to the
other client during an online session.

**Rationale:** 
Communicating information besides inputs is often very important. For example,
sending information about the other player's username allows it to be displayed
ingame.

**Fit Criterion:** 
The module has an exposed function which adds extra data to be sent alongside
input information, in the next packet. Whenever it receives extra data from the
client, it emits a signal containing the data, which the rest of the game code
can receive and process.

**Priority:** 
Medium

**Dependencies:** 
Requirement #07

Requirement #16
===============

**Type:** 
Functional

**Description:** 
The module should provide a way for the user to specify a variable in the
game's state data as a check for desyncs.

**Rationale:** 
Often, games which use this type of netcode (where only input data is sent back
and forth, and calculations such as physics are handled locally by each client)
will transmit a small amount of game state data to ensure that both clients are
in sync regarding their individual local calculations. For example, if the data
for a character's position is different between the two clients, then the game
knows that they have drifted out of sync, and it can end the game early and
throw a desync error.

**Fit Criterion:** 
The module has an exposed function to set a specific variable (or combination
of variables) as the desync check, and will then send it in packets and compare
against the other client's value. It emits a signal when a desync is detected.

**Priority:** 
Medium

**Dependencies:** 
Requirement #07

Requirement #17
===============

**Type:** 
Functional

**Description:** 
The module should allow clients to connect via IP.

**Rationale:** 
Connecting via IP is the simplest way to connect for game testing purposes. The
user can then implement server-based matchmaking and feed the resulting IP into
the module.

**Fit Criterion:** 
The module has an exposed function to start a new session and try to connect to
another client at a given IP address.

**Priority:** 
Essential

**Dependencies:** 
Requirement #07

Requirement #18
===============

**Type:** 
Usability / Ease of Use

**Description:** 
The module should present itself as a wrapped-up "class" that can easily be
used in game code.

**Rationale:** 
Framing the module as an object in code will make it very easy to use and
understand.

**Fit Criterion:** 
The module is implemented as a class in Godot which can be instanced, and
whose functions can be called to perform all of the module's functionality.

**Priority:** 
High

**Dependencies:** 
(none)

Requirement #19
===============

**Type:** 
Maintainability and Support

**Description:** 
The module's code should be clean and easy to maintain.

**Rationale:** 
Maintainable code is good and helps extend the life of a project. It makes it
easier to fix bugs and add features.

**Fit Criterion:** 
The module's C++ code follows reasonable guidelines for code formatting and
structure, e.g. [these](https://github.com/cpp-best-practices/cppbestpractices/blob/master/00-Table_of_Contents.md).

**Priority:** 
High

**Dependencies:** 
(none)

Requirement #20
===============

**Type:** 
Functional

**Description:** 
The module should include functionality for a "read-only" client type, e.g. a
spectator in a game session.

**Rationale:** 
A spectator feature is common in online games, where you can watch a game you
aren't participating in. This requirement being met would allow the addition
of spectator features without introducing unnecessary load from processing the
spectator client as if it were a player (e.g. receiving meaningless game
inputs).

**Fit Criterion:** 
The module can add IP addresses as spectator clients, which do not send inputs;
they only receive input data (and sync/misc data) for the purpose of keeping a
local copy of the game state.

**Priority:** 
Low

**Dependencies:** 
Requirement #07