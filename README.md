# Orleans Best Practices Kata
Welcome to the Orleans Best Practices Kata! This kata is designed to teach you the best practices in Microsoft Orleans using a collaborative, interactive approach. 

[//]: # (You'll be implementing parts of an Evercraft RPG game and see how your solutions perform in a shared arena.)

## Tasks
### Stateless vs. Stateful Grains

#### Objective
Learn when to use stateless versus stateful grains.

#### Scenario:
In the game, we need a grain responsible for combat calculations and another for managing player stats and inventory .
#### Task
Implement a combat calculator and character grains
- `Player` - An actor that manages player stats and actions;
- `Combat` - An actor that calculates combat results based on player stats and actions.
- `Inventory` - An actor that manages player inventory and items.

#### Discussion
> After implementation, discuss why certain grains are stateless and others are stateful. Highlight scenarios where one might accidentally choose the wrong type and how it could affect performance or scalability.

### Oneway Grain Calls
#### Objective
Learn when to use oneway calls to improve performance and reduce latency.

#### Scenario
In a fast-paced battle sequence, We want to send updates or notifications to all players, For instance, broadcasting damage updates to multiple players in an arena.

#### Task
Create a `Quest` actor,which sends a notification to all players when a monster is defeated, randomly select a player to receive a weapen reward.

#### Discussion
> After participants have implemented this, discuss the implications of using oneway calls, such as the inability to know if a message was successfully processed, and the scenarios where this trade-off is acceptable.

### Grain Sequence Control
#### Objective
Learn how to manage grain sequences and ensure proper ordering of operations.

#### Scenario
Implement a quest system where a character must complete tasks in sequence (e.g., gather items, craft a weapon, then slay a monster). The sequence should enforce that step B can't start until step A is completed, and step C only begins after B.

#### Task
[//]: # ( `Armor` grains  )
1. Implement a `Waraxe`grain, `Knife`grain, and a `Monster` grain
2. `Waraxe` & `Knife`grains, should have an attack method that attack a specific monster.
3. `Monster` should have a health property that can be reduced by an attack method.
4. `Player` should attack a monster with available weapon of his inventory when a `Monster` arrived.


### Event Sourcing with Orleans
#### Objective
Learn event sourcing using Orleans for state management.

#### Scenario
Implement an event-sourced `InventoryGrain` where each action (adding or removing items) generates an event. This grain should be able to rebuild its state by replaying these events.

#### Task
Build the grain and test its ability to recover state after failure or restarts by replaying events.

#### Discussion
> After the exercise, discuss the pros and cons of using event sourcing, the complexity it introduces, and how it fits with Orleans' distributed architecture.


#### Discussion
> Discuss how Orleans handles task sequencing and what to consider when designing grains that depend on the order of operations. Also, cover potential pitfalls like cyclical dependencies and how to avoid them.

### Handling Failures and Retries
#### Objective
Learn best practices in handling grain failures and implementing retries.

#### Scenario
Imagine a scenario where a grain responsible for a critical game feature (like saving progress) fails intermittently due to network issues or other transient failures.

#### Task
Implement a `SaveGameGrain` that simulates a failure. Participants need to implement retries using Orleans' built-in mechanisms.

#### Discussion
> Discuss the importance of idempotency in grains, how to ensure grains can handle retries without corrupting state, and when to escalate errors.

  









## Repository Setup 

<a alt="Nx logo" href="https://nx.dev" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/nrwl/nx/master/images/nx-logo.png" width="45"></a>

✨ **This workspace has been generated by [Nx](https://nx.dev)** and [@nx-dotnet](https://www.nx-dotnet.com/docs/)

### Quick Start
#### install dependencies

`pnpm install`, `npm install`,  or `yarn install` to install the dependencies.

Then, run `pnpm start`, `npm start`,  or `yarn start` to start the API and the client app. 

### Projects
- [api](./api) - ASP.NET Core Web API application
- [grains](./grains) - Orleans Grains
- [grain-tests](./grain-tests) - Test project for the Orleans Grains

### Generated Code
- [generated/docs](./generated/docs/references) - Docfx - dotnet documentation, generated from the source code
- [generated/api-swagger](./generated/api-swagger) - OpenAPI spec for the API, generated from the ASP.NET Core Web API
- [generated/ts-client](./generated/ts-client) - Typescript client code for the API, generated from the OpenAPI spec

  