# teamTitans

Beta: apple crumble
Technologies:
Unity3d -- game engine, will be used to glue together entire app
Vuforia -- ML portion, used for 3D models, logo detection, object recognition(?), other CV -computer vision- aspects of game
Cloud SQL -- hopefully integrated with PostgreSQL, database to be linked to project
** MySQL if we run into problems with CloudSQL
Photon Unity Networking (PUN) -- framework for multi-user Unity app capability, potentially used for login? (Further research required)
C# -- language for writing scripts in Unity
** Object recognition model from Tensorflow -- only necessary in the case that Vuforia object recognition is no longer feasible
** ARKit / ARCore -- augments experience on mobile? (Further research required, may already be used in Vuforia)
QR code generator / reader -- Further research required
UnityUI -- develop GUI for user to use app seamlessly and intuitively

TIER 1 ISSUES:
User signup/login persists a user in the database (with unique* handle) -- and logout (in preparation for Tier 2 only/low priority)
QR code to be generated that will initialize first quest and NPC
Script (C#) to initialize first quest and NPC ^ likely will be achieved by attaching this to a QR code via generator
Geofence or other boundary marker to indicate adequate distance to talk to NPCs
NPC speech and text to be written
NPC should address user by handle e.g. “Oh, it’s you, `${user.name}`! ~~ I haven’t had lunch yet and it would be wonderful if you could go fetch me a snack, and find out where that mischievous boy of mine is.”
Dialog box for user screen: “Accept / reject”
Reject: “Too busy? Hmph. Young people these days.”
Accept: “Ah, how kind of you! Please bring me back an apple, some Starbucks, and that no-good son of mine!”
Dialog box for user: “...”
NPC: “Oh? You look a bit confused! Here, let me show you how to use --insert fantasy name of tool here--, it must have been a while since you’ve last been around.”
-- AT MINIMUM, dialog boxes pointing to buttons appear OR swipe through tutorial screen for capturing objects --
User needs to be able to use ‘capture mode’ -- point camera at logos/take pictures and submit them to app for detection (Vuforia)
User needs to have associated ‘Badges’ that persist -- also should have associated Quests that have been accepted with bool for In progress/Completed
UI design needs to include AT MINIMUM → Quest log to view quests in progress and what items still need to be found, Badge box with all prior badges (IN ORDER!!!), button for capture mode, ? button for controls

FIRST DRAFT:
AR narrative/adventure game:
 - Users walk up to hard-coded NPCs in locations around the area/city and receive scavenger hunt quests from them
- Quests can involve finding other NPCs, finding places, or finding items
- Users take photos of requested items/signboards for places and app checks using object classification NNs and logo detection
- Upon quest completion users receive badges for that particular quest, as well as location hints for next NPC
- Other feature ideas include quests that involve altering target object and receiving effects on person e.g. taking a picture of an apple with a bite out of it and health goes up
- Possible integration of sprites that appear over specific logos/items as quest objects

MVP:
- Users can sign up and login in
- Users can start first quest via QR code scan
- NPC spawns in same room as user
- User needs to walk up to the NPC to talk to them
- NPC assigns a tutorial quest to find 1 object, 1 place, and 1 other NPC, and shows demo for how to capture objects (photos for object, place camera over for location scan, find NPC) 
- Upon completion, quest badge received by player



MVP Official Statement: 
## AR Adventure/narrative quest-based game

## Overview: Users walk up to NPCs in various locations and receive scavenger hunt quests from them. Users must find objects, locations, or other NPCs to complete their quests.

### MVP: 
Tier 1:
Users can sign up and log in
Users can start their first quest by scanning a QR code
NPC appears in the same room as user upon QR scan
User must walk up to NPC to ‘talk’ to them and receive a quest
User can choose to accept or refuse the quest
NPC assigns a tutorial quest to find 1 object, 1 place, and 1 other NPC, and shows on-screen demonstration for how to capture objects (pointing camera at, taking photo of, walking up to NPC, etc.)
Upon completion (all 3 items found), the player receives a quest badge (accomplishment) able to viewed in badge box
