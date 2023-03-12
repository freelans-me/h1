# h1
homework1
<task1>
class Pet:
    def __init__(self, name, species, age):
        self.name = name
        self.species = species
        self.age = age
        self.is_hungry = False
        self.mood = "happy"

    def __str__(self):
        return f"{self.name} is a {self.species} aged {self.age}"

    def feed(self):
        self.is_hungry = False
        self.mood = "happy"

    def play(self):
        self.mood = "happy"

    def mood_status(self):
        if self.is_hungry:
            return f"{self.name} is {self.mood} but hungry."
        else:
            return f"{self.name} is {self.mood} and not hungry."

pet1 = Pet("Tom", "cat", 2)
print(pet1)
print(pet1.mood_status())

pet1.is_hungry = True
print(pet1.mood_status())

pet1.feed()
print(pet1.mood_status())

pet1.play()
print(pet1.mood_status())

import random
<task2>
class Student:
    def __init__(self, name, money):
        self.name = name
        self.money = money
        self.health = 100
        self.knowledge = 0
        self.working = False

    def work(self):
        self.money += random.randint(50, 200)
        self.knowledge -= 5
        self.health -= 5
        self.working = True

    def rest(self):
        if self.money >= 100:
            self.money -= 100
            self.health += 10
            self.working = False

    def study(self):
        if self.money >= 200:
            self.money -= 200
            self.knowledge += 20
            self.health -= 5

    def live(self):
        while self.health > 0 and self.knowledge < 100 and self.money >= 0:
            if self.money < 50 and not self.working:
                self.work()
            elif self.health < 50 and not self.working:
                self.rest()
            elif self.knowledge < 50 and self.money >= 200:
                self.study()
            else:
                self.rest()
        if self.health <= 0:
            print(f"{self.name} is dead.")
        elif self.knowledge >= 100:
            print(f"{self.name} graduated!")
        else:
            print(f"{self.name} is broke.")
