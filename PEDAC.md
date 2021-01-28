Problem:

Create an API that allows the user to create and care for a virtual pet

CRUD
C: Create a pet through POST/pets
R: Read all the pets through GET/pets and Read a specific pet by id through GET/pets/{id}
U: Update a specific pet by id through PUT/pets/{id}
D: Delete a specific pet by id through DELETE/pets/{id}

Examples:

GET /pets: returns all pets in your database.
GET /pets/{id},:returns the pet with the corresponding id.
POST /pets: creates a new pet. The body of the request should contain a JSON object with a key of "name" and a value of the pet's name. The pets Birthday should default to the current DateTime, HungerLevel defaults to 0 and HappinessLevel defaults to 0.
PUT/pets/{id}: updates a pet from the database by Id
DELETE /pets/{id}: deletes a pet from the database by Id
POST /pets/{id}/playtimes: find the pet by id and add 5 to its happiness level and add 3 to its hungry level. It should also create a new Playtime for this pet and the current time.
POST /pets/{id}/feedings: find the pet by id and subtract 5 from its hungry level and add 3 to its happiness level. It should also create a new Feeding for this pet and the current time.
POST /pets/{id}/scoldings: find the pet by id and subtract 5 from its happiness level. It should also create a new Scolding for this pet and the current time.

Data Structure:

Pet (Model)
Id: int
Name: string
Birthday: DateTime
HungerLevel: int
HappinessLevel: int
public List<Playtime> Playtimes { get; set; }
public List<Feeding> Feedings { get; set; }
public List<Scolding> Scoldings { get; set; }

Playtime (Model)
Id: int
When: DateTime
PetId: int
Pet TheAssociated Pet {get; set;}

Feeding (Model)
Id: int
When: DateTime
PetId: int
Pet TheAssociated Pet {get; set;}

Scolding (Model)
Id: int
When: DateTime
PetId: int
Pet TheAssociated Pet {get; set;}

Under DatabaseContext.cs
Public DbSet<Pet> Pets {get; set;}
Public DbSet<Playtime> Playtimes {get; set;}
Public DbSet<Feeding> Feedings {get; set;}
Public DbSet<Scolding> Scoldings {get; set;}
