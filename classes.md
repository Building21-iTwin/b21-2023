# Introduction to Classes in JavaScript/TypeScript

In JavaScript and TypeScript, Classes provide a way to define blueprints for creating objects with shared properties and behaviors. They are used to encapsulate data and functionality into reusable components, making it easier to manage and maintain code.
Let's say we want to create a game with different types of characters, such as Paladins and Wizards. We can use Classes to define the common properties and methods that these characters share.
To create a Class in TypeScript, we use the class keyword followed by the name of the class, in this case, Character. Inside the class, we can define properties and methods using the constructor and other methods.
If you recall, the constructor is what gets called when we use the special `new` keyword to generate a new _instance_ of this class.
Here's an example:

```typescript
class Character {
  name: string;
  health: number;
  power: number;

  constructor(name: string, health: number, power: number) {
    this.name = name;
    this.health = health;
    this.power = power;
  }

  attack(target: Character) {
    target.health -= this.power;
    console.log(
      `${this.name} attacked ${target.name} for ${this.power} damage!`
    );
  }

  heal(amount: number) {
    this.health += amount;
    console.log(`${this.name} healed for ${amount} health!`);
  }
}

// create a new instance of a Character using the 'new' keyword
// This calls the Character's "constructor" method.
// We pass parameters which correspond to each of the constructor's parameters: name, health, and power.
const imp = new Character("Generic Imp", 1, 1);

// we create another imp
const blueImp = new Character("Blue Imp", 2, 1);

// A key feature of classes is that when you create instances from them, the instances are separate entities:
// the imp's name, health, and power are completely separate from the blueImp's name, health, and power.

// Remember, we spoke about 'comments' as well! They are parts of the code which are never read by the computer.
// This right here is a comment - they are often used to clarify or explain what a piece of code does.
```

In this example, the Character class has three "properties": name, health, and power, which are defined with their types. It also has two "methods": attack, which takes a target parameter of type Character and reduces the target's health by the power of the attacking character, and heal, which takes an amount parameter of type number and increases the health of the character.

We spoke last week about how methods are sort of like verbs - they do something, and how properties are like nouns - they're things.

Now, let's say we want to create subclasses of Character for Paladins and Wizards. We can do this using the extends keyword, which allows us to inherit properties and methods from the parent class. We can also add new properties and methods to the subclass.

Here's an example of how we might define the Paladin subclass:

```typescript
class Paladin extends Character {
  faith: number;

  constructor(name: string, health: number, power: number, faith: number) {
    super(name, health, power); // the "super" keyword calls the "base" class's constructor
    this.faith = faith;
  }

  smite(target: Character) {
    target.health -= this.power + this.faith;
    console.log(
      `${this.name} smote ${target.name} for ${this.power + this.faith} damage!`
    );
  }
}

const colin = new Paladin("Colin Kerr", 100, 10, 1);
const keith = new Paladin("Keith", 1000, 40 10);

keith.attack(colin); // colin's health is now 60, since it was 100 and Keith's power is 40.
keith.smite(colin); // colin's health is now 10
```

In this example, the Paladin class extends Character using the extends keyword. It adds a new property, faith, and a new method, smite, which deals damage to the target using the Paladin's power and faith.

We could also define a Wizard subclass in a similar way, with its own unique properties and methods. Properties themselves can be other Classes.

```typescript
class Spell {
  name: string;
  power: number;
  cost: number;

  constructor(name: string, power: number, cost: number) {
    this.name = name;
    this.power = power;
    this.cost = cost;
  }
}

class Wizard extends Character {
  constructor(
    name: string,
    health: number,
    power: number,
    mana: number,
    spells: Spell[] // an example of an array of Spells. See [types.md](./types.md) for more information about arrays.
  ) {
    super(name, health, power);
    this.spells = spells;
    this.mana = mana;
  }

  cast(spellName: string, target: Character) {
    if (!this.hasSpell(spellName)) return; // the Wizard doesn't have access to this spell!

    target.health = target.health - spell.power;
    this.mana = this.mana - spell.cost;

    console.log(
      `${this.name} casted spell ${spell.name} on ${target.name} for ${spell.power} damage!`
    );

    console.log(
      `Casting spell ${spell.name} cost ${this.name} for ${spell.cost} mana. ${this.name} now has ${this.mana} mana.`
    );
  }

  hasSpell(spellName: string): boolean {
    // the "find" method goes through each item an an array, in this case the spells array,
    // and looks for an item which satisfies the condition specified.
    // Here, we're looking for a spell whose name is equal to the name passed into this method.
    const foundSpell = this.spells.find((spell) => spell.name === spellName);
    return foundSpell; // if found, this variable will hold the name of the spell. If not found, this will not be defined.
  }
}

const merlinSpells: Spell[] = [new Spell("fire", 20), new Spell("thunder", 15)];
const merlin = new Wizard("Merlin", 500, 1, 100, merlinSpells);
const colin = new Paladin("Colin Kerr", 100, 10, 1);

merlin.cast("fire", colin);
```
