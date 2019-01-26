# UNIT 3 FINAL: PART TWO

In this part, you will be building a Pokemon API. Think of this as a simplified version of the Pokemon Go API. There is no authentication or middleware needed.

## Models:
- Towns
  - id
  - name
- Trainers
  - id
  - name
  - hometown_id
- Pokemons
  - id
  - trainer_id
  - name
  - level
  - type_1
  - type_2

The seed file is already created for you: [seed.sql](./seed.sql). It is populated with many towns, trainers and pokemons. 

**You MAY NOT modify the database schema.**

## Routes High Level

You may run and test all these routes with this premade Postman collection: 

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/bfd492a0ffb5b74d963e)

### Town:
- `GET /town/:name/trainers/`: Gets all the trainers from that hometown

### Trainer:
- `POST /trainer/`: Creates a new trainer
- `GET /trainer/:name`: Gets the trainer with the name
- `PUT /trainer/:name`: Updates the trainer with the name
- `DELETE /trainer/:name`: Deletes the trainer with the name
- `GET /trainer/:name/pokemons`: Returns all the pokemon owned by trainer
- `GET /trainer/:name/pokemons?levelmin=50`: Returns all the pokemon owned by trainer greater or equal to level

### Pokemon:
- `POST /pokemon/`: Creates a new pokemon
- `GET /pokemon/:id`: Gets the pokemon with the id
- `PUT /pokemon/:id`: Updates the pokemon with the id
- `DELETE /pokemon/:id`: Deletes the pokemon with the id
- `GET /pokemon/:type/all`: Returns all pokemon of that type from either type_1 or type_2 

## Routes & Responses

### Town

#### `GET /town/Pallet Town/trainers/`

```javascript
[
    {
        "id": 1,
        "name": "Ash",
        "hometown_id": 1,
        "hometown_name": "Pallet Town"
    },
    {
        "id": 2,
        "name": "Gary",
        "hometown_id": 1,
        "hometown_name": "Pallet Town"
    }
]
```

### Trainer

#### `POST /trainer/`

Request Body: 
```
name: Mo
hometown: 2
```

Response
```javascript
{
    "success": "Created trainer named Mo with generated ID: 11"
}
```

#### `GET /trainer/Ash`

```javascript
{
    "id": 1,
    "name": "Ash",
    "hometown_id": 1,
    "hometown_name": "Pallet Town"
}
```

#### `PUT /trainer/Mo`

Request Body: 
```
hometown: 3
```

Response
```javascript
{
    "success": "Updated trainer named Mo with hometown ID: 3"
}
```

#### `DELETE /trainer/Mo`

```javascript
{
    "success": "Deleted trainer named Mo"
}
```

#### `GET /trainer/Gary/pokemons`

```javascript
[
    {
        "id": 7,
        "trainer_id": 2,
        "name": "Blastoise",
        "level": 85,
        "type_1": "water",
        "type_2": null,
        "trainer_name": "Gary"
    },
    {
        "id": 8,
        "trainer_id": 2,
        "name": "Nidoqueen",
        "level": 80,
        "type_1": "poison",
        "type_2": "ground",
        "trainer_name": "Gary"
    },
    {
        "id": 9,
        "trainer_id": 2,
        "name": "Arcanine",
        "level": 80,
        "type_1": "fire",
        "type_2": null,
        "trainer_name": "Gary"
    },
    {
        "id": 10,
        "trainer_id": 2,
        "name": "Electabuzz",
        "level": 70,
        "type_1": "electric",
        "type_2": null,
        "trainer_name": "Gary"
    }
]
```

#### `GET /trainer/Gary/pokemons?levelmin=85`

```javascript
[
    {
        "id": 7,
        "trainer_id": 2,
        "name": "Blastoise",
        "level": 85,
        "type_1": "water",
        "type_2": null,
        "trainer_name": "Gary"
    }
]
```

### Pokemon

#### `POST /pokemon/`

Request Body: 
```
trainer: 1
name: Charmander
level: 5
type_1: fire
```

Response
```javascript
{
    "success": "Created Pokemon named Charmander with generated ID: 39"
}
```

#### `GET /pokemon/39`

```javascript
{
    "id": 39,
    "trainer_id": 1,
    "name": "Charmander",
    "level": 5,
    "type_1": "fire",
    "type_2": null,
    "trainer_name": "Ash"
}
```

#### `PUT /pokemon/39`

Request Body: 
```
trainer: 1
name: Charmeleon
level: 16
type_1: fire
```

Response
```javascript
{
    "success": "Updated pokemon named Charmeleon with trainer ID: 1"
}
```

#### `DELETE /pokemon/39`

```javascript
{
    "success": "Deleted pokemon with ID: 39"
}
```

#### `GET /pokemon/fire/all`

```javascript
[
    {
        "id": 2,
        "trainer_id": 1,
        "name": "Charizard",
        "level": 80,
        "type_1": "fire",
        "type_2": "flying",
        "trainer_name": "Ash"
    },
    {
        "id": 9,
        "trainer_id": 2,
        "name": "Arcanine",
        "level": 80,
        "type_1": "fire",
        "type_2": null,
        "trainer_name": "Gary"
    },
    {
        "id": 36,
        "trainer_id": 10,
        "name": "Arcanine",
        "level": 48,
        "type_1": "fire",
        "type_2": null,
        "trainer_name": "Blaine"
    },
    {
        "id": 35,
        "trainer_id": 10,
        "name": "Ninetales",
        "level": 47,
        "type_1": "fire",
        "type_2": null,
        "trainer_name": "Blaine"
    },
    {
        "id": 34,
        "trainer_id": 10,
        "name": "Rapidash",
        "level": 47,
        "type_1": "fire",
        "type_2": null,
        "trainer_name": "Blaine"
    },
    {
        "id": 33,
        "trainer_id": 10,
        "name": "Magmar",
        "level": 47,
        "type_1": "fire",
        "type_2": null,
        "trainer_name": "Blaine"
    }
]
```
