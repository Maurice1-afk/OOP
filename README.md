# OOP

/*Assignment 1: Design Your Own Class!*/
# Base class
class Hero:
    def __init__(self, name, power, level):
        self.name = name
        self.power = power
        self._level = level  # Encapsulated (protected) attribute

    def introduce(self):
        print(f"I am {self.name}, my power is {self.power}!")

    def use_power(self):
        print(f"{self.name} uses {self.power} at level {self._level}!")

    def level_up(self):
        self._level += 1
        print(f"{self.name} leveled up! New level: {self._level}")

# Subclass with polymorphic behavior
class FlyingHero(Hero):
    def __init__(self, name, power, level, max_altitude):
        super().__init__(name, power, level)
        self.max_altitude = max_altitude

    # Override use_power (Polymorphism)
    def use_power(self):
        print(f"{self.name} soars through the skies using {self.power} up to {self.max_altitude} meters!")

# Create Hero objects
hero1 = Hero("ShadowStrike", "Invisibility", 3)
hero2 = FlyingHero("SkyBlade", "Flight", 5, 10000)

# Use their methods
hero1.introduce()
hero1.use_power()
hero1.level_up()

print("—" * 40)

hero2.introduce()
hero2.use_power()
hero2.level_up()


/*Activity 2: Polymorphism Challenge!*/
# Base class
class Vehicle:
    def move(self):
        print("The vehicle is moving...")

# Subclasses with their own version of move()
class Car(Vehicle):
    def move(self):
        print("Driving on the road 🚗")

class Plane(Vehicle):
    def move(self):
        print("Flying in the sky ✈️")

class Boat(Vehicle):
    def move(self):
        print("Sailing on the water 🚢")

# List of different vehicles
vehicles = [Car(), Plane(), Boat()]

# Loop through and call move() polymorphically
for v in vehicles:
    v.move()

