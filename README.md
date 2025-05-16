class Superhero:
    def __init__(self, name, power, health):
        self.name = name
        self.power = power
        self.health = health

    def attack(self, target):
        print(f"{self.name} attacks {target.name} with a power of {self.power}!")
        target.take_damage(self.power)

    def take_damage(self, damage):
        self.health -= damage
        print(f"{self.name} takes {damage} damage. Current health: {self.health}")
        if self.health <= 0:
            print(f"{self.name} has been defeated!")

class FlyingSuperhero(Superhero):
    def __init__(self, name, power, health, wingspan):
        super().__init__(name, power, health)
        self.wingspan = wingspan

    def fly(self):
        print(f"{self.name} soars through the sky with a wingspan of {self.wingspan} meters!")

# Creating instances
superman = Superhero("Superman", 100, 150)
wonder_woman = Superhero("Wonder Woman", 90, 160)
hawkman = FlyingSuperhero("Hawkman", 80, 120, 5)

# Demonstrating methods
superman.attack(wonder_woman)
wonder_woman.attack(superman)
hawkman.fly()
hawkman.attack(superman)





class Car:
    def move(self):
        print("Driving on the road 🚗")

class Plane:
    def move(self):
        print("Flying through the air ✈️")

class Boat:
    def move(self):
        print("Sailing on the water 🛥️")

def let_them_move(vehicle):
    vehicle.move()

# Creating instances of different vehicles
my_car = Car()
my_plane = Plane()
my_boat = Boat()

# Demonstrating polymorphism
vehicles = [my_car, my_plane, my_boat]
for vehicle in vehicles:
    let_them_move(vehicle)
    
