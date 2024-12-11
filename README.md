java cCS-107: Mini-project 2
Cooperative games
Version 1.2
Contents
1 Introduction 4
2 ICoop de base ICoop Basics (Step 1) 7
2.1 Preparing the ICoop ICoop . . . . . . . . . . . . . . . . . . . . . . . . . . . 7
2.2 Adaptation of ICoopBehavior . . . . . . . . . . . . . . . . . . . . . . . . . . 8
2.2.1 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
2.3 Draft of Main Characters . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
2.3.1 Drawing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.3.2 Behavior . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.3.3 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
2.4 Doors: Contact Interactions . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
2.4.1 Doors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11
2.4.2 ICoopPlayer as an Interactor . . . . . . . . . . . . . . . . . . . . . 12
2.4.3 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
2.5 Second Character . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
2.5.1 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
2.6 Explosives: Remote Interactions . . . . . . . . . . . . . . . . . . . . . . . . . 14
2.6.1 Obstacles and Explosives . . . . . . . . . . . . . . . . . . . . . . . . 14
2.6.2 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
2.7 Reset . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
2.7.1 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
2.8 Validation of Step 1 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
3 First Cooperation (Step 2) 17
13.1 Health Bar . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
3.1.1 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
3.2 Dialogues . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
3.2.1 Activating a Dialogue . . . . . . . . . . . . . . . . . . . . . . . . . . 20
3.2.2 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
3.3 Collectible Items . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
3.3.1 Collecting Explosives . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
3.3.2 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
3.3.3 The ElementalItem . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
3.3.4 The Orbs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
3.3.5 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
3.4 Elemental Walls . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
3.4.1 Elemental Category Role . . . . . . . . . . . . . . . . . . . . . . . . . 23
3.4.2 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
3.5 Assistance, Healing, and Invulnerability Periods . . . . . . . . . . . . . . . . 24
3.5.1 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
3.6 Maze Area . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
3.6.1 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
3.7 Validation of Step 2 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
4 Enemies and Battles (Step 3) 26
4.1 Equipment . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
4.1.1 Inventory Items . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
4.1.2 Inventories . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
4.1.3 Collection and Inventory . . . . . . . . . . . . . . . . . . . . . . . . . 28
4.1.4 Graphics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
4.1.5 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
4.2 Enemies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
4.2.1 Projectiles . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
4.2.2 Fire-throwing Skulls . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
4.2.3 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
4.2.4 Bomber . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
4.2.5 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 34
4.3 Battles . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
4.3.1 Staffs and Water/Fire Orbs . . . . . . . . . . . . . . . . . . . . . . . 35
24.3.2 Tasks . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
4.3.3 Weapon Usage by Characters . . . . . . . . . . . . . . . . . . . . . . 35
4.3.4 Tasks . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
4.4 Validation of Step 3 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
5 Final challenge (Step 4) 38
5.1 Keys and Teleporters . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
5.2 Area Arena . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
5.3 Gateway to the manor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
5.4 Task . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 40
5.5 Validation of Step 4 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
6 Extensions (Step 5) 42
6.1 New actors or character extensions . . . . . . . . . . . . . . . . . . . . . . . 42
6.2 Pause, game ending and ‘reset’(~2 to 5pts) . . . . . . . . . . . . . . . . . . 43
6.3 Validation of Step 5 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 44
6.4 Contest . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 44
7 Appendices 45
7.1 KeyBindings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
7.2 Basic Conffguration of the Maze Area . . . . . . . . . . . . . . . . . . . . . . 45
7.3 Creating Animations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 46
7.3.1 ICoopPlayer . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 46
7.3.2 Explosive . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
7.3.3 Orbs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
7.3.4 Hearts . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
7.3.5 Staves . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
7.3.6 Flames . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
7.3.7 Water or Fire Projectiles . . . . . . . . . . . . . . . . . . . . . . . . . 49
7.3.8 Death of foes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
7.3.9 Fire-Shooting Skulls . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
7.3.10 Artiffcers . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
31 Introduction
This document uses colors and contains clickable links. It is best
viewed in digital format.
Over the past weeks, you have become familiar with the fundamentals of a small ad-hoc
game engine (see tutorial) that allows you to create tile-based games in two dimensions,
similar to RPGs.
The goal of this mini-project is to leverage this knowledge to create one or more small
concrete implementations of a cooperative variant named ICcoOp, a type of game involving
two main characters. These characters will collaborate to achieve objectives or defeat
enemies. The base game you are tasked with creating is inspired by games like Fireboy and
Watergirl. Figure 1 shows some fragments of the basic draft that you can then enrich as you
wish, according to your imagination and creativity. Section 6 also includes a short video
example of a potential game you could create.
Beyond its entertaining aspect, this mini-project will naturally allow you to practice the
fundamental concepts of object-oriented programming. It will let you experience how a
design situated at an appropriate level of abstraction enables the creation of programs that
are easily extensible and adaptable to different contexts.
You will progressively increase the complexity of the desired features and the interactions
between components, step by step.
The project consists of four mandatory steps and one optional step:
• Step 1 (”Basic Game”): By the end of this step, you will have created, using the tools
of the provided game engine, a basic instance of ICCoOp where two main characters
can follow each other from one area to another and interact with objects.
• Step 2 (”First Cooperation”): During this step, the two characters will begin to assist
each other in facing hostile walls. Rudimentary dialogues will be introduced, along
with tracking the characters’ health points.
• Step 3 (”Belligerent Adversaries”): This step will enable your characters to face
enemies and engage in battles with them using equipment.
• Step 4 (”Final Challenges”): This step will introduce new areas with new challenges
to tackle cooperatively, utilizing the concept of logical signals.
• Step 5 (Optional Extensions): During this step, various more open-ended extensions
will be proposed, allowing you to enhance the game created in the previous step or to
create new games of your own design.
Code a few extensions (of your choice) to earn bonus points and/or
participate to the contest.
4Figure 1: Some scenes from the game where two players help each other from area to area,
collecting items and battling various hostile (or not) creatures.
Here are the main instructions/guidelines to follow for coding the project:
1. You will not modify the code of game-engine. Beware of
IntelliJ’s «quick ffx» proposal.
2. The project must be coded using standard Java tools (imports
starting with java. or javax.). If you have doubts about
using a particular library, ask us, and be especially cautious
with the alternatives IntelliJ might suggest importing on your
machine. The project speciffcally uses the Color class. You
must use the java.awt.Color implementation and not other
implementations from various alternative packages.
3. Your methods must be documented according to Javadoc standards
 (refer to the the class TextGraphics of game-engine for
inspiration).
4. Your code must adhere to standard naming conventions and
be properly modularized and encapsulated. In particular,
avoid intrusive public getters on modiffable objects.
(continued on the next page . . .)
54. The instructions provided may sometimes be very detailed.
This does not mean they are exhaustive. The methods
and attributes needed to achieve the desired functionalities are
not all described, and it will be up to you to introduce them as
you see fit, ensuring proper encapsulation.
5. Your project must not be stored on a public repository
(e.g., GitHub). For those familiar with Git, we recommend
using GitLab: https://gitlab.epfl.ch/, but any repository type
is acceptable as long as it is private.
The first step is deliberately guided. Its primary goal is to deepen your understanding of
the provided framework and to begin leveraging it in a concrete manner.
62 ICoop de base ICoop Basics (Step 1)
The goal of this step is to start creating your own game of the ICoop type.
This basic version will include two main characters that can be controlled individually and
are capable of interacting with objects. The latter point will be implemented using the more
general mechanism of interactions between actors, as described in tutorial 3.
This game will involve:
• Two main characters;
• Doors that the characters can pass through. This will involve a contact interaction: a
character must be in a cell containing an ”actor” labeled as a ”door” to pass through
it;
• An explosive that the characters can activate (via remote interaction);
• a rock that the explosive, once activated, can destroy (again via remote interaction).
The two characters will follow each other during area transitions.
You will work in the provided icoop package.
2.1 Preparing the ICoop ICoop
The solution for the tutorial is provided in the tutos folder, and you
can use it as inspiration to get started.
Prepare an ICoop game inspired by Tuto2. This game will initially consist of :
• The ICoopPlayer class, which models a main character, should be placed in icoop.actor;
leave this class empty for now, we will come back to it a bit later;
• the ICoop class, equivalent to Tuto2, to be placed in the icoop package; don’t forget
to adapt the getTitle() method, which will return a name of your choice (e.g.,
"ICoop");
• une classe ICoopArea équivalente à Tuto2Area, à placer dans un sous-paquetage
icoop.area;
• A class ICoopArea equivalent to Tuto2Area, to be placed in a sub-package icoop.area;
• Classes Spawn and OrbWay inheriting from ICoopArea, to be placed in the package
icoop.area (they are equivalent to the classes Ferme or Village in the tutorial). For
the title, use "Spawn" and "OrbWay" to ensure proper alignment with the graphical
resources;
• A class ICoopBehavior analogous to Tuto2Behavior to be placed in icoop, which
will contain a public class ICoopCell equivalent to Tuto2Cell.
You will ensure that the initial positions of the main characters to come are dictated by a
method returning specific values for each area: for example, (13,6) for the red character
and (14,6) for the blue one in the area Spawn, and (1,12) and (1,5) for the area OrbWay.
For the type of games we’re interested in, it is best to centre the view as closely as possible
in the window. To do this, simply add the following redefinition to ICoopArea :
7@Override
public boolean isViewCentered() { return true; }
2.2 Adaptation of ICoopBehavior
First, a few updates need to be made to the classes ICoopBehavior and ICoopCell. The
enumerated type describing the cell types will have an additional field indicating whether
the cell can be flown over or not (a canWalk field, similar to isWalkable, and a canFly field
indicating if one can fly over the cell and which can be used later in the project) :
NULL(0, false , false),
WALL(-16777216, false , false),
IMPASSABLE (-8750470, false , true),
INTERACT(-256, true , true),
DOOR(-195580, true , true),
WALKABLE(-1, true , true),
ROCK(-16777204, true , true),
OBSTACLE (-16723187, true , true)
Additionally, the nature of the cells will not be the only factor determining whether a cell
allows an actor to enter (via its method canEnter). The actors already present in the cell
will also play a role. In the case of the ICoop game, a cell can have at most one non-passable
actor within its set of entities (inherited from Cell): two non-passable actors cannot coexist
in the same cell !
The takeCellSpace() method indicates whether an actor is passable (allows others to ”step
on it”) or not. It is passable if its takeCellSpace() method returns false.
Make the suggested adaptations above in the ICoopBehavior class.
2.2.1 Task
You are required to implement the concepts described above according to the given specifications
and constraints. Run your ICoop game. Verify that the empty area in Figure 2 is
displayed.
2.3 Draft of Main Characters
For now, code ICoopPlayer in the same spirit as GhostPlayer.
One important difference is that the characters, like many upcoming actors, will ”serve” a
natural element (typically the ”water” or ”fire” element).
You should therefore introduce a category called ElementalEntity. Any actor behaving
as an ElementalEntity must define a method element() that returns the natural element
the actor serves. This will, of course, apply to the ma代 写CS-107、java
代做程序编程语言in characters. The element served by
the character will be specified during construction.
8Figure 2: Welcome area
2.3.1 Drawing
Another significant difference from GhostPlayer is that the image used to draw an ICoopPlayer
will depend on its orientation and will be animated.
To draw the character, you will use an object of type OrientedAnimation. There will be
several possible animations as the project progresses, but for now, only the basic animation
needs to be implemented. This can be constructed as described in Appendix 7.3.11
. Since we
will create two characters, the name of the image used to create the animation will naturally
differ for each. You should consider this name as configurable during the character’s
construction.
2.3.2 Behavior
An ICoopPlayer is a non-passable actor that is oriented downward by default. It behaves
(updates itself) like a MoveableAreaEntity but with additional features:
• It must be movable using keys, similar to the GhostPlayer coded in the tutorial;
• Its current animation must also be updated based on the following algorithm: if a
movement is in progress, the current animation must undergo an update; otherwise,
it must undergo a reset.
One of the unique aspects of ICoop games is that two characters need to be controlled,
requiring two different sets of keys. The specific set of keys for a given character can be configured
during construction as a KeyBinding.PlayerKeyBindings. Refer to Appendix 7.1 to
understand this data type. Adapt your movement method so that the ”directional arrow”
keys used in the tutorial are replaced by keys.up(), keys.down(), keys.right(), and
keys.left(), where keys is the set of keys associated with the character.
Once this draft of ICoopPlayer is complete, you can start adapting the begin method of
ICoop and testing your game. Initially, you will introduce only one of the two characters.
At launch, a player of type ICoopPlayer will be created at its designated position in
1Refer to the documentation for OrientedAnimation if you want to understand the role of the parameters
in creating the animation.
9Figure 3: Door from “Spawn” area to “OrbWay” area
the current area. The name of the images associated with its basic animation will be
"icoop/player", and the keys used to control it will be those specified by
KeyBindings.RED_PLAYER_KEY_BINDINGS.
2.3.3 Task
You are required to code the concepts described above according to the given specifications
and constraints.
Run your ICoop game. Verify that it behaves as shown in the following short video:
https://proginsc.epfl.ch/wwwhiver/mini-projet2/videos/icoop/startStep1.mp4. Specifically,
ensure that:
1. The game starts by displaying an ICoopPlayer facing forward;
2. The character can move freely across the area using the keys specified by
KeyBindings.RED_PLAYER_KEY_BINDINGS (W, A, S, and D if unchanged) but cannot
leave the area;
3. Its graphical representation adapts correctly to its orientation;
4. Its movements are animated.
2.4 Doors: Contact Interactions
You are now tasked with applying the interaction framework suggested in the third part of
the tutorial (Clickable Link)2
.
The first interaction we will focus on is a contact interaction with a ”door” actor that will
allow an ICoopPlayer to transition from one area to another.
2A complementary video is also available to explain the implementation of interactions: mp2-
interactions.mp4
102.4.1 Doors
As explained in the tutorial, if an entity undergoes interactions, it must be modeled as an
Interactable; if it initiates interactions, it must be modeled as an Interactor (and it can
be both).
As a first category of Interactable, we already have ICoopCell (for example, if a character
is in contact with certain types of cells, it could adopt a different behavior, such as sliding).
We will not exploit this feature for now but will instead introduce a new Interactable,
”door,” which will have a more immediate utility.
A door, Door, to be coded in the icoop.actor package, is an actor of type AreaEntity
that allows transitions to a destination area.
This actor is characterized by:
• the name of the area to which it allows a transition (a string);
• and the set of arrival coordinates (DiscreteCoordinates) in the destination area.
This set will be variable in size, though for the purposes of this project, it will typically
have a size of two : arrival coordinates for the red character followed by those for the
blue one.
The tutorial introduced the notion of a signal, which can be used here to make the game
more engaging by incorporating puzzle-solving elements. For example, to obtain a weapon
for defense, the character might need to find a key that opens a door to a room containing
the desired weapon. The provided tools could typically catalog a key actor as a signal
attached to this door: once the signal is activated (the key is picked up), the door opens.
A ”door” actor will therefore also be characterized by a signal (of type Logic) that models
the conditions under which it is open or closed.
The constructor for a Door takes the following parameters: the name of the destination area,
the signal conditioning its opening, the possible arrival coordinates in the destination area,
the area it belongs to, the position of its main cell, and optionally the list of coordinates
of the cells it occupies in addition to its main cell (expressed using an ellipsis in a second
constructor).
The method getCurrentCells() must therefore be overridden in Door to return the set of
these occupied coordinates.
A Door is a passable actor that accepts contact interactions and whose drawing method
does nothing by default. Indeed, doors will coincide with elements of the scenery and will
not be drawn as distinct entities. As a result, their orientation is not very important.
You are tasked with introducing this new actor and registering an instance of it with the
following characteristics in the Spawn area:
destination arrival coord. signal main cell other coord.
”OrbWay” (1,12)(1,5) Logic.TRUE (19,15) (19,16)
This amounts to placing a door at the location indicated in Figure 3.
Also, register the doors that allow the transition in the other direction, from OrbWay to
Spawn:
11destination arrival coord. Signal main cell other coord.
”Spawn” (18,16),(18,15) Logic.TRUE (0,14) (0,13),(0,12),(0,11), (0,10)
”Spawn” (18,16),(18,15) Logic.TRUE (0,8) (0,7), (0,6), (0,5), (0,4)
The value Logic.TRUE indicates that these doors are open without any condition. The
locations of the doors can be determined by counting the coordinates of the red tiles in the
”behavior” images (for example, see resources/images/behaviors/Spawn.png).
2.4.2 ICoopPlayer as an Interactor
Now that we have a concrete entity capable of undergoing interactions, let’s focus on
ICoopPlayer as an entity initiating interactions. Start by ensuring that all ICoopPlayer
instances become Interactor entities (they can initiate interactions with Interactable
entities).
As an Interactor, ICoopPlayer must define the following methods:
• getCurrentCells(): its current cells, which are reduced to the set containing only
its main cell (as you have already implemented);
• getFieldOfViewCells(): the cells forming its field of view, consisting of the single
cell it is facing:
Collections.singletonList
(getCurrentMainCellCoordinates().jump(getOrientation().toVector()));
As an Interactor, it will always request all contact interactions (wantsCellInteraction
always returns true). Whether it requests remote interactions (wantsViewInteraction)
will be determined by the user: pressing its keyBindings.useItem() key will indicate that
the character wants a remote interaction. For example, if a character is facing an explosive
and the user wants to activate it, they press the key corresponding to keyBindings.useItem()
(by default, E for the red player and O for the blue player).
We can now handle the possible interactions at this stage: in the subpackage icoop.handler,
complete the ICoopInteractionVisitor interface, which inherits from AreaInteractionVisitor.
This interface must provide default definitions for the interactWith methods for all Interactor
entities in the ICoop game with:
• a game cell (ICoopCell);
• a main character in the game (ICoopPlayer);
• a door (Door).
These (default) definitions will have an empty body to indicate that, by default, the interaction
does nothing (ICoopPlayer, as an Interactor in the ICoop game, must provide a
more specific definition of these methods if necessary).
Every concrete Interactable must now indicate that it accepts having its interactions
managed by an interaction handler of type ICoopInteractionVisitor.
void acceptInteraction(AreaInteractionVisitor v, boolean
isCellInteraction) {
((ICoopInteractionVisitor) v).interactWith(this ,
isCellInteraction);
}
12This method may contain more code depending on the case, but for now, it is suﬀicient for
the three types of Interactable available: ICoopPlayer, ICoopCell, and Door.
To allow ICoopPlayer to manage interactions of interest more specifically, define a private
nested class ICoopPlayerInteractionHandler inside the ICoopPlayer class, implementing
ICoopInteractionVisitor. Add the necessary definitions to handle interactions with doors
more precisely, such that during a contact interaction with a door, if the door’s signal is
activated (method isOn()), the character:
1. leaves its current area (method leaveArea());
2. arrives in the destination area at the first possible arrival coordinate for that area
(method setCurrentArea).
Note: Only the game knows all the areas and is capable of transitioning the character
from one area to another using the leaveArea and setCurrentArea methods. Therefore,
this process cannot be directly coded in the character’s interaction method with the door.
Instead, the method should only inform the character that it is traversing a door (and specify
which one), and the character must provide the necessary information to the game!
2.4.3 Task
You are required to implement the concepts and processes described above according to the
given specifications and constraints. Run your ICoop game. Verify that the main character
can transition from the "Spawn" room to the "OrbWay" room (and vice versa) through the
location corresponding to the door in Figure 3. The lower door in the OrbWay room will
only be reachable once the second character is introduced.
2.5 Second Character
We now introduce what makes ICoop games unique: the presence of a second character.
The introduction of this character raises the question of how to properly center the camera,
which until now has followed the single character as in the tutorial.
The adopted idea is to center the camera on a point equidistant from the two characters.
To simplify the required calculations, a CenterOfMass actor is provided.
You are now tasked with evolving the ICoop game to:
• include a second character as a core feature;
• ensure that the begin method creates this character and centers the camera on a
CenterOfMass object constructed using the two characters.
The second character will:
• start at the position dictated for them in the current area;
• use the image "icoop/player2" as their associated sprite;
• be controlled with the keys specified by KeyBindings.BLUE_PLAYER_KEY_BINDINGS.
If this character transitions via a door, it must arrive at the second arrival coordinate in
the destination area. Additionally, ensure that the two characters follow each other: if one
13character passes through a door, the other follows, arriving at the destination coordinate
assigned to them by the door. Both characters will always occupy the same area!
Finally, to ensure that the initially chosen scale factor does not hinder the joint observation
of both characters, the update method of the game dynamically recalculates it (and reassigns
it using setCameraScaleFactor) with a heuristic formula such as:
max(DEFAULT_SCALE_FACTOR, DEFAULT_SCALE_FACTOR * 0.75
+ distance(position_playerA, position_playerB) / 2)
You are free to refine this formula as you see fit. The distance can be calculated as the length
of the vector position_playerA - position_playerB (methods sub and getLength of
Vector).
2.5.1 Task
Once the suggested modifications have been implemented, run your ICoop game. Verify
that :
• a second character appears at the start of the game;
• it can be controlled using its specific key bindings;
• it behaves like the first character but is drawn with a blue-tinted animation;
• each character can transition from "Spawn" to "OrbWay" and vice versa. In this case,
the other character follows, and both characters arrive in the area at the positions
designated for them by the crossed door. An example of a door passage is provided
in the following video:
https://proginsc.epfl.ch/wwwhiver/mini-projet2/videos/icoop/secondPlayer.mp4.
2.6 Explosives: Remote Interactions
To solidify the interaction management mechanism, the final part of this step involves
introducing two new actors: explosives and obstacles, with the idea that an explosive can
destroy certain obstacles remotely.
2.6.1 Obstacles and Explosives
An obstacle is an actor derived from AreaEntity and drawable by default using the sprite
"rock.2". By default, it is non-passable and it unconditionally accepts any type of interaction.
Rocks are a specific type of obstacle, drawable using the sprite "rock.1", and they
can be destroyed: they are non-passable and are only drawn if they are not destroyed.
An explosive is a passable actor inheriting from AreaEntity and playing the role of an
Interactor. It can be activated and is associated with a timer (an integer) initialized at
its creation. It is created in a deactivated state. Once activated, on each of its update, its
timer is decremented (e.g., by one unit). When the timer reaches zero, the explosion occurs
(the explosive enters the explosion state), which triggers the display of a specific animation,
after which it disappears from the game.
14An explosive, as an Interactor, requests remote or contact interactions when it is in the
explosion state. For now, it interacts remotely only with rocks. The effect of the interaction
with rocks is, of course, to destroy them.
The explosive’s field of action, getFieldOfViewCells(), consists of all 4 cells immediately
adjacent vertically and horizontally to its main cell. getCurrentCells() should be coded
in the same way as for ICoopPlayer.
As an Interactable, an explosive can undergo remote interactions if it has not exploded,
and contact interactions only if it is neither activated nor exploded.
Graphically, the explosive can be represented with an animation. It must disappear after
 its explosion, which should be accompanied by another specific animation. Refer to
Appendix 7.3.2 for more precise details on this.
Finally, ensure that when a character interacts remotely with an explosive, it becomes
activated. Remember that characters express the desire for a remote interaction using their
useItem() key (default: 'E' and 'O' respectively).
To complete this step, create an explosive and a rock at respective positions (11,10) and
(10,10) in Spawn.
2.6.2 Task
You are required to implement the concepts described above according to the given specifications
and constraints.
Run your ICoop game. Verify that it behaves as shown in the following short video:
https://proginsc.epfl.ch/wwwhiver/mini-projet2/videos/icoop/step1Explosion.mp4; specifically:
•
 that characters cannot pass through the rock but can pass through the explosive;
• that each character can activate the explosive vi         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
