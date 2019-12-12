## Introduction
This is a collection of JSON snippets that are used to brain-storm the flow of data in [Serge](github.com/serge/web/serge)

## Game Design
We're short-circuiting this phase initially.  Two areas of the Serge Admin pages relate to game design.  In **Platform Types** the game designer descsribes the _types_ of participant that will take part in the game, and how they're described within the game.  See an example in [Platform Types](platform_types.json).

The second area is where platforms are assigned to forces. Within each force, the game designer will create a set of platforms. Each platform is of a platform type, and includes specific details for that instance.   See an example of how the set of forces are defined in [Forces](forces.json)

The above JSON snippets will be merged into an existing wargame definition document.

The following message types all result in modifications to the above wargame design document.  For example, at the end of a planning phase, the "planned route" for a platform in a force will be updated with the new planned route.

## Force Laydown
At the start of a game, red is able to adjust the position of it's assets. We're calling this the _force laydown_.  The end of this process is when the force laydown message is sent.  This fills in the positional specifics for the red platforms. See an example in [Red Laydown](red_laydown.json)

## Initial Resolution
Before game-play starts, the umpire sets the initial visibility of platforms.  This is done by working through all the platforms, and indicating whether they are initially visible to Blue and/or Red.  An example of this initial resolution is in [Initial Resolution](initial_resolution.json)

## Planning phase
In this phase, red and blue plan what their platforms will do in the next 30 minute cycle. They do this by giving the platforms routes to follow, and maybe triggering some actions.  An example of this is in [red_orders](red_orders.json)

Also during the planning phase, one force may develop a perception of which force a platform belongs to.  A prime example of this a platform of unknown allegiance being changed to Green, or a Green Dhow being changed to Red, based on analysis of their behaviour.  An example of this message is in [force perception](force_perception.json)

## Resolution phase
Once the orders have been submitted, the umpire must resolve the turn.  This is done by analysing the demanded routes, and producing a new state.  This new state will include new positions for all platforms, maybe new planned routes (or maybe just _consuming_ the current step of the route), and may include changes in visibility for platforms, or platform states (such as disabled).  An example of the state change message is in [state](state.json) 
