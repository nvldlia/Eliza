---
id: "SqlJsDatabaseAdapter"
title: "Class: SqlJsDatabaseAdapter"
sidebar_label: "SqlJsDatabaseAdapter"
sidebar_position: 0
custom_edit_url: null
---

An abstract class representing a database adapter for managing various entities
like accounts, memories, actors, goals, and rooms.

## Hierarchy

- [`DatabaseAdapter`](DatabaseAdapter.md)

  ↳ **`SqlJsDatabaseAdapter`**

## Constructors

### constructor

• **new SqlJsDatabaseAdapter**(`db`): [`SqlJsDatabaseAdapter`](SqlJsDatabaseAdapter.md)

#### Parameters

| Name | Type       |
| :--- | :--------- |
| `db` | `Database` |

#### Returns

[`SqlJsDatabaseAdapter`](SqlJsDatabaseAdapter.md)

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[constructor](DatabaseAdapter.md#constructor)

## Properties

### db

• **db**: `Database`

## Methods

### addParticipant

▸ **addParticipant**(`user_id`, `room_id`): `Promise`\<`boolean`\>

Adds a user as a participant to a specific room.

#### Parameters

| Name      | Type                                                       | Description                                           |
| :-------- | :--------------------------------------------------------- | :---------------------------------------------------- |
| `user_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the user to add as a participant.         |
| `room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the room to which the user will be added. |

#### Returns

`Promise`\<`boolean`\>

A Promise that resolves to a boolean indicating success or failure.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[addParticipant](DatabaseAdapter.md#addparticipant)

---

### countMemories

▸ **countMemories**(`room_id`, `unique?`, `tableName?`): `Promise`\<`number`\>

Counts the number of memories in a specific room.

#### Parameters

| Name        | Type                                                       | Default value | Description                                       |
| :---------- | :--------------------------------------------------------- | :------------ | :------------------------------------------------ |
| `room_id`   | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | `undefined`   | The UUID of the room for which to count memories. |
| `unique`    | `boolean`                                                  | `true`        | Specifies whether to count only unique memories.  |
| `tableName` | `string`                                                   | `""`          | Optional table name to count memories from.       |

#### Returns

`Promise`\<`number`\>

A Promise that resolves to the number of memories.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[countMemories](DatabaseAdapter.md#countmemories)

---

### createAccount

▸ **createAccount**(`account`): `Promise`\<`boolean`\>

Creates a new account in the database.

#### Parameters

| Name      | Type                                  | Description                   |
| :-------- | :------------------------------------ | :---------------------------- |
| `account` | [`Account`](../interfaces/Account.md) | The account object to create. |

#### Returns

`Promise`\<`boolean`\>

A Promise that resolves when the account creation is complete.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[createAccount](DatabaseAdapter.md#createaccount)

---

### createGoal

▸ **createGoal**(`goal`): `Promise`\<`void`\>

Creates a new goal in the database.

#### Parameters

| Name   | Type                            | Description                |
| :----- | :------------------------------ | :------------------------- |
| `goal` | [`Goal`](../interfaces/Goal.md) | The goal object to create. |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the goal has been created.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[createGoal](DatabaseAdapter.md#creategoal)

---

### createMemory

▸ **createMemory**(`memory`, `tableName`): `Promise`\<`void`\>

Creates a new memory in the database.

#### Parameters

| Name        | Type                                | Description                                  |
| :---------- | :---------------------------------- | :------------------------------------------- |
| `memory`    | [`Memory`](../interfaces/Memory.md) | The memory object to create.                 |
| `tableName` | `string`                            | The table where the memory should be stored. |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the memory has been created.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[createMemory](DatabaseAdapter.md#creatememory)

---

### createRelationship

▸ **createRelationship**(`params`): `Promise`\<`boolean`\>

Creates a new relationship between two users.

#### Parameters

| Name           | Type                                                       | Description                                                        |
| :------------- | :--------------------------------------------------------- | :----------------------------------------------------------------- |
| `params`       | `Object`                                                   | An object containing the UUIDs of the two users (userA and userB). |
| `params.userA` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                                  |
| `params.userB` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                                  |

#### Returns

`Promise`\<`boolean`\>

A Promise that resolves to a boolean indicating success or failure of the creation.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[createRelationship](DatabaseAdapter.md#createrelationship)

---

### createRoom

▸ **createRoom**(`room_id?`): `Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`\>

Creates a new room with an optional specified ID.

#### Parameters

| Name       | Type                                                       | Description                              |
| :--------- | :--------------------------------------------------------- | :--------------------------------------- |
| `room_id?` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | Optional UUID to assign to the new room. |

#### Returns

`Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`\>

A Promise that resolves to the UUID of the created room.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[createRoom](DatabaseAdapter.md#createroom)

---

### getAccountById

▸ **getAccountById**(`user_id`): `Promise`\<`null` \| [`Account`](../interfaces/Account.md)\>

Retrieves an account by its ID.

#### Parameters

| Name      | Type                                                       | Description                               |
| :-------- | :--------------------------------------------------------- | :---------------------------------------- |
| `user_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the user account to retrieve. |

#### Returns

`Promise`\<`null` \| [`Account`](../interfaces/Account.md)\>

A Promise that resolves to the Account object or null if not found.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getAccountById](DatabaseAdapter.md#getaccountbyid)

---

### getActorDetails

▸ **getActorDetails**(`params`): `Promise`\<[`Actor`](../interfaces/Actor.md)[]\>

Retrieves details of actors in a given room.

#### Parameters

| Name             | Type                                                       | Description                                            |
| :--------------- | :--------------------------------------------------------- | :----------------------------------------------------- |
| `params`         | `Object`                                                   | An object containing the room_id to search for actors. |
| `params.room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                      |

#### Returns

`Promise`\<[`Actor`](../interfaces/Actor.md)[]\>

A Promise that resolves to an array of Actor objects.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getActorDetails](DatabaseAdapter.md#getactordetails)

---

### getCachedEmbeddings

▸ **getCachedEmbeddings**(`opts`): `Promise`\<\{ `embedding`: `number`[] ; `levenshtein_score`: `number` }[]\>

Retrieves cached embeddings based on the specified query parameters.

#### Parameters

| Name                        | Type     | Description                                                  |
| :-------------------------- | :------- | :----------------------------------------------------------- |
| `opts`                      | `Object` | An object containing parameters for the embedding retrieval. |
| `opts.query_field_name`     | `string` | -                                                            |
| `opts.query_field_sub_name` | `string` | -                                                            |
| `opts.query_input`          | `string` | -                                                            |
| `opts.query_match_count`    | `number` | -                                                            |
| `opts.query_table_name`     | `string` | -                                                            |
| `opts.query_threshold`      | `number` | -                                                            |

#### Returns

`Promise`\<\{ `embedding`: `number`[] ; `levenshtein_score`: `number` }[]\>

A Promise that resolves to an array of objects containing embeddings and levenshtein scores.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getCachedEmbeddings](DatabaseAdapter.md#getcachedembeddings)

---

### getGoals

▸ **getGoals**(`params`): `Promise`\<[`Goal`](../interfaces/Goal.md)[]\>

Retrieves goals based on specified parameters.

#### Parameters

| Name                     | Type                                                                 | Description                                         |
| :----------------------- | :------------------------------------------------------------------- | :-------------------------------------------------- |
| `params`                 | `Object`                                                             | An object containing parameters for goal retrieval. |
| `params.count?`          | `number`                                                             | -                                                   |
| `params.onlyInProgress?` | `boolean`                                                            | -                                                   |
| `params.room_id`         | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`           | -                                                   |
| `params.user_id?`        | `null` \| \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                   |

#### Returns

`Promise`\<[`Goal`](../interfaces/Goal.md)[]\>

A Promise that resolves to an array of Goal objects.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getGoals](DatabaseAdapter.md#getgoals)

---

### getMemories

▸ **getMemories**(`params`): `Promise`\<[`Memory`](../interfaces/Memory.md)[]\>

Retrieves memories based on the specified parameters.

#### Parameters

| Name               | Type                                                       | Description                                               |
| :----------------- | :--------------------------------------------------------- | :-------------------------------------------------------- |
| `params`           | `Object`                                                   | An object containing parameters for the memory retrieval. |
| `params.count?`    | `number`                                                   | -                                                         |
| `params.room_id`   | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                         |
| `params.tableName` | `string`                                                   | -                                                         |
| `params.unique?`   | `boolean`                                                  | -                                                         |

#### Returns

`Promise`\<[`Memory`](../interfaces/Memory.md)[]\>

A Promise that resolves to an array of Memory objects.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getMemories](DatabaseAdapter.md#getmemories)

---

### getParticipantsForAccount

▸ **getParticipantsForAccount**(`user_id`): `Promise`\<[`Participant`](../interfaces/Participant.md)[]\>

Retrieves participants associated with a specific account.

#### Parameters

| Name      | Type                                                       | Description              |
| :-------- | :--------------------------------------------------------- | :----------------------- |
| `user_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the account. |

#### Returns

`Promise`\<[`Participant`](../interfaces/Participant.md)[]\>

A Promise that resolves to an array of Participant objects.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getParticipantsForAccount](DatabaseAdapter.md#getparticipantsforaccount)

---

### getParticipantsForRoom

▸ **getParticipantsForRoom**(`room_id`): `Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`[]\>

Retrieves participants for a specific room.

#### Parameters

| Name      | Type                                                       | Description                                              |
| :-------- | :--------------------------------------------------------- | :------------------------------------------------------- |
| `room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the room for which to retrieve participants. |

#### Returns

`Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`[]\>

A Promise that resolves to an array of UUIDs representing the participants.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getParticipantsForRoom](DatabaseAdapter.md#getparticipantsforroom)

---

### getRelationship

▸ **getRelationship**(`params`): `Promise`\<`null` \| [`Relationship`](../interfaces/Relationship.md)\>

Retrieves a relationship between two users if it exists.

#### Parameters

| Name           | Type                                                       | Description                                                        |
| :------------- | :--------------------------------------------------------- | :----------------------------------------------------------------- |
| `params`       | `Object`                                                   | An object containing the UUIDs of the two users (userA and userB). |
| `params.userA` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                                  |
| `params.userB` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                                  |

#### Returns

`Promise`\<`null` \| [`Relationship`](../interfaces/Relationship.md)\>

A Promise that resolves to the Relationship object or null if not found.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getRelationship](DatabaseAdapter.md#getrelationship)

---

### getRelationships

▸ **getRelationships**(`params`): `Promise`\<[`Relationship`](../interfaces/Relationship.md)[]\>

Retrieves all relationships for a specific user.

#### Parameters

| Name             | Type                                                       | Description                                |
| :--------------- | :--------------------------------------------------------- | :----------------------------------------- |
| `params`         | `Object`                                                   | An object containing the UUID of the user. |
| `params.user_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                          |

#### Returns

`Promise`\<[`Relationship`](../interfaces/Relationship.md)[]\>

A Promise that resolves to an array of Relationship objects.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getRelationships](DatabaseAdapter.md#getrelationships)

---

### getRoom

▸ **getRoom**(`room_id`): `Promise`\<`null` \| \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`\>

Retrieves the room ID for a given room, if it exists.

#### Parameters

| Name      | Type                                                       | Description                       |
| :-------- | :--------------------------------------------------------- | :-------------------------------- |
| `room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the room to retrieve. |

#### Returns

`Promise`\<`null` \| \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`\>

A Promise that resolves to the room ID or null if not found.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getRoom](DatabaseAdapter.md#getroom)

---

### getRoomsForParticipant

▸ **getRoomsForParticipant**(`user_id`): `Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`[]\>

Retrieves room IDs for which a specific user is a participant.

#### Parameters

| Name      | Type                                                       | Description           |
| :-------- | :--------------------------------------------------------- | :-------------------- |
| `user_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the user. |

#### Returns

`Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`[]\>

A Promise that resolves to an array of room IDs.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getRoomsForParticipant](DatabaseAdapter.md#getroomsforparticipant)

---

### getRoomsForParticipants

▸ **getRoomsForParticipants**(`userIds`): `Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`[]\>

Retrieves room IDs for which specific users are participants.

#### Parameters

| Name      | Type                                                         | Description                     |
| :-------- | :----------------------------------------------------------- | :------------------------------ |
| `userIds` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`[] | An array of UUIDs of the users. |

#### Returns

`Promise`\<\`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\`[]\>

A Promise that resolves to an array of room IDs.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[getRoomsForParticipants](DatabaseAdapter.md#getroomsforparticipants)

---

### log

▸ **log**(`params`): `Promise`\<`void`\>

Logs an event or action with the specified details.

#### Parameters

| Name             | Type                                                       | Description                                        |
| :--------------- | :--------------------------------------------------------- | :------------------------------------------------- |
| `params`         | `Object`                                                   | An object containing parameters for the log entry. |
| `params.body`    | `Object`                                                   | -                                                  |
| `params.room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                  |
| `params.type`    | `string`                                                   | -                                                  |
| `params.user_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                  |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the log entry has been saved.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[log](DatabaseAdapter.md#log)

---

### removeAllGoals

▸ **removeAllGoals**(`room_id`): `Promise`\<`void`\>

Removes all goals associated with a specific room.

#### Parameters

| Name      | Type                                                       | Description                                         |
| :-------- | :--------------------------------------------------------- | :-------------------------------------------------- |
| `room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the room whose goals should be removed. |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when all goals have been removed.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[removeAllGoals](DatabaseAdapter.md#removeallgoals)

---

### removeAllMemories

▸ **removeAllMemories**(`room_id`, `tableName`): `Promise`\<`void`\>

Removes all memories associated with a specific room.

#### Parameters

| Name        | Type                                                       | Description                                            |
| :---------- | :--------------------------------------------------------- | :----------------------------------------------------- |
| `room_id`   | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the room whose memories should be removed. |
| `tableName` | `string`                                                   | The table from which the memories should be removed.   |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when all memories have been removed.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[removeAllMemories](DatabaseAdapter.md#removeallmemories)

---

### removeGoal

▸ **removeGoal**(`goalId`): `Promise`\<`void`\>

Removes a specific goal from the database.

#### Parameters

| Name     | Type                                                       | Description                     |
| :------- | :--------------------------------------------------------- | :------------------------------ |
| `goalId` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the goal to remove. |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the goal has been removed.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[removeGoal](DatabaseAdapter.md#removegoal)

---

### removeMemory

▸ **removeMemory**(`memoryId`, `tableName`): `Promise`\<`void`\>

Removes a specific memory from the database.

#### Parameters

| Name        | Type                                                       | Description                                        |
| :---------- | :--------------------------------------------------------- | :------------------------------------------------- |
| `memoryId`  | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the memory to remove.                  |
| `tableName` | `string`                                                   | The table from which the memory should be removed. |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the memory has been removed.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[removeMemory](DatabaseAdapter.md#removememory)

---

### removeParticipant

▸ **removeParticipant**(`user_id`, `room_id`): `Promise`\<`boolean`\>

Removes a user as a participant from a specific room.

#### Parameters

| Name      | Type                                                       | Description                                               |
| :-------- | :--------------------------------------------------------- | :-------------------------------------------------------- |
| `user_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the user to remove as a participant.          |
| `room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the room from which the user will be removed. |

#### Returns

`Promise`\<`boolean`\>

A Promise that resolves to a boolean indicating success or failure.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[removeParticipant](DatabaseAdapter.md#removeparticipant)

---

### removeRoom

▸ **removeRoom**(`room_id`): `Promise`\<`void`\>

Removes a specific room from the database.

#### Parameters

| Name      | Type                                                       | Description                     |
| :-------- | :--------------------------------------------------------- | :------------------------------ |
| `room_id` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | The UUID of the room to remove. |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the room has been removed.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[removeRoom](DatabaseAdapter.md#removeroom)

---

### searchMemories

▸ **searchMemories**(`params`): `Promise`\<[`Memory`](../interfaces/Memory.md)[]\>

Searches for memories based on embeddings and other specified parameters.

#### Parameters

| Name                     | Type                                                       | Description                                            |
| :----------------------- | :--------------------------------------------------------- | :----------------------------------------------------- |
| `params`                 | `Object`                                                   | An object containing parameters for the memory search. |
| `params.embedding`       | `number`[]                                                 | -                                                      |
| `params.match_count`     | `number`                                                   | -                                                      |
| `params.match_threshold` | `number`                                                   | -                                                      |
| `params.room_id`         | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                      |
| `params.tableName`       | `string`                                                   | -                                                      |
| `params.unique`          | `boolean`                                                  | -                                                      |

#### Returns

`Promise`\<[`Memory`](../interfaces/Memory.md)[]\>

A Promise that resolves to an array of Memory objects.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[searchMemories](DatabaseAdapter.md#searchmemories)

---

### searchMemoriesByEmbedding

▸ **searchMemoriesByEmbedding**(`_embedding`, `params`): `Promise`\<[`Memory`](../interfaces/Memory.md)[]\>

Searches for memories by embedding and other specified parameters.

#### Parameters

| Name                      | Type                                                       | Description                           |
| :------------------------ | :--------------------------------------------------------- | :------------------------------------ |
| `_embedding`              | `number`[]                                                 | The embedding vector to search with.  |
| `params`                  | `Object`                                                   | Additional parameters for the search. |
| `params.count?`           | `number`                                                   | -                                     |
| `params.match_threshold?` | `number`                                                   | -                                     |
| `params.room_id?`         | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                     |
| `params.tableName`        | `string`                                                   | -                                     |
| `params.unique?`          | `boolean`                                                  | -                                     |

#### Returns

`Promise`\<[`Memory`](../interfaces/Memory.md)[]\>

A Promise that resolves to an array of Memory objects.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[searchMemoriesByEmbedding](DatabaseAdapter.md#searchmemoriesbyembedding)

---

### updateGoal

▸ **updateGoal**(`goal`): `Promise`\<`void`\>

Updates a specific goal in the database.

#### Parameters

| Name   | Type                            | Description                              |
| :----- | :------------------------------ | :--------------------------------------- |
| `goal` | [`Goal`](../interfaces/Goal.md) | The goal object with updated properties. |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the goal has been updated.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[updateGoal](DatabaseAdapter.md#updategoal)

---

### updateGoalStatus

▸ **updateGoalStatus**(`params`): `Promise`\<`void`\>

Updates the status of a specific goal.

#### Parameters

| Name            | Type                                                       | Description                                         |
| :-------------- | :--------------------------------------------------------- | :-------------------------------------------------- |
| `params`        | `Object`                                                   | An object containing the goalId and the new status. |
| `params.goalId` | \`$\{string}-$\{string}-$\{string}-$\{string}-$\{string}\` | -                                                   |
| `params.status` | [`GoalStatus`](../enums/GoalStatus.md)                     | -                                                   |

#### Returns

`Promise`\<`void`\>

A Promise that resolves when the goal status has been updated.

#### Overrides

[DatabaseAdapter](DatabaseAdapter.md).[updateGoalStatus](DatabaseAdapter.md#updategoalstatus)
