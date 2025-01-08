<!-- ChatGPT Coding Diary
Project Name: Object Oriented Adventures Project
Date: 12/20/2024 -->

We first started making the foundational classes for the game such as the main character class and enemy class.
class Maincharacter:
    def __init__(self, name, inventory, money, hp, attack):
        self.name = name
        self.inventory = inventory
        self.money = money
        self.hp = hp
        self.attack = attack
class Enemy:
    def __init__(self, ename, ehp, eattack, espeed):
        self.name = ename
        self.ehp = ehp
        self.eattack = eattack
        self.espeed = espeed
What I wanted to do was to add more features to these classes such as dying, attacking, etc
So I asked chatgpt to create a class for my player class that had taking damage in it
it gave me 
class Maincharacter:
    def __init__(self, name, inventory, money, hp, attack):
        self.name = name
        self.inventory = inventory
        self.money = money
        self.hp = hp
        self.attack = attack
        self.is_alive = True
    def take_damage(self, eattack):
        self.health -= eattack
        print(f"{self.name} takes {eattack} damage!")
        if self.health <= 0:
            self.is_alive = False
            self.die()
            print(f"{self.name} has been defeated!")
Chatgpt gave me a baseplate for creating more features such as dying and attacking now. However, one complaint I have with this is that the taking damage feature works for turn based games but not real time games I want. Also the lines that get printed feel too strange but that is easily changeable.
After getting this code I was able to create buying, attacking, dying, and losing items.
class Maincharacter:
    def __init__(self, name, inventory, money, hp, attack):
        self.name = name
        self.inventory = inventory
        self.money = money
        self.hp = hp
        self.attack = attack
        self.is_alive = True

    def buy(self, item, money):
        self.inventory.append(item)
        print(self.inventory)
        self.inventory.remove(money)
        
    def attack_enemy(self, enemy):
        damage = max(0, self.attack)  # Basic attack calculation
        print(f"{self.name} attacks {enemy.name} for {damage} damage!")
        enemy.take_damage(damage)

    def take_damage(self, eattack):
        self.health -= eattack
        print(f"{self.name} takes {eattack} damage!")
        if self.health <= 0:
            self.is_alive = False
            self.die()
            # print(f"{self.name} has been defeated!")

    def die(self):
        print(f"{self.name} has died! hahaha loser")
        self.lose_items()

    def lose_items(self):
        items_to_keep = [special]

        self.inventory = [item for item in self.inventory if item in items_to_keep]

        self.money = 0
        
        print(f"{self.name} has died and lost all their stuff hahahaha")
        print(f"Remaining items: {self.inventory}")
        print(f"Remaining money: {self.money}")
Through chatgpt I was able to learn how to add basically any feature to a class I want. 

<!-- ChatGPT Coding Diary
Project Name: Object Oriented Adventures Project
Date: 1/2/2025 -->

