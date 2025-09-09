Got it 👍
Your Java code is an example of the **Factory Method Pattern**. I’ll translate this into **Python** while keeping the same structure and behavior.

In Python, we don’t have `interface` and `implements` keywords like Java, but we can use **abstract base classes (ABC)** from the `abc` module to mimic them.

Here’s the equivalent **Python code**:

```python
from abc import ABC, abstractmethod

# --- Product Interface ---
class Burger(ABC):
    @abstractmethod
    def prepare(self):
        pass


# --- Concrete Products ---
class BasicBurger(Burger):
    def prepare(self):
        print("Preparing Basic Burger with bun, patty, and ketchup!")


class StandardBurger(Burger):
    def prepare(self):
        print("Preparing Standard Burger with bun, patty, cheese, and lettuce!")


class PremiumBurger(Burger):
    def prepare(self):
        print("Preparing Premium Burger with gourmet bun, premium patty, cheese, lettuce, and secret sauce!")


class BasicWheatBurger(Burger):
    def prepare(self):
        print("Preparing Basic Wheat Burger with bun, patty, and ketchup!")


class StandardWheatBurger(Burger):
    def prepare(self):
        print("Preparing Standard Wheat Burger with bun, patty, cheese, and lettuce!")


class PremiumWheatBurger(Burger):
    def prepare(self):
        print("Preparing Premium Wheat Burger with gourmet bun, premium patty, cheese, lettuce, and secret sauce!")


# --- Factory Interface ---
class BurgerFactory(ABC):
    @abstractmethod
    def create_burger(self, type: str) -> Burger:
        pass


# --- Concrete Factories ---
class SinghBurger(BurgerFactory):
    def create_burger(self, type: str) -> Burger:
        if type.lower() == "basic":
            return BasicBurger()
        elif type.lower() == "standard":
            return StandardBurger()
        elif type.lower() == "premium":
            return PremiumBurger()
        else:
            print("Invalid burger type!")
            return None


class KingBurger(BurgerFactory):
    def create_burger(self, type: str) -> Burger:
        if type.lower() == "basic":
            return BasicWheatBurger()
        elif type.lower() == "standard":
            return StandardWheatBurger()
        elif type.lower() == "premium":
            return PremiumWheatBurger()
        else:
            print("Invalid burger type!")
            return None


# --- Client Code ---
if __name__ == "__main__":
    burger_type = "basic"

    factory: BurgerFactory = SinghBurger()   # You can switch to KingBurger()
    burger = factory.create_burger(burger_type)

    if burger:
        burger.prepare()
```

### ✅ Key Notes

* Used `ABC` and `@abstractmethod` to mimic **interfaces**.
* Methods use **snake\_case** instead of camelCase (Python convention).
* Instead of `System.out.println`, we use `print()`.
* In the client code, you can change `factory = SinghBurger()` to `KingBurger()` to switch.

---

Do you want me to also show you a **simplified Python version** (without abstract classes, just duck typing), or do you want to stick to the more **Java-like strict version** with `ABC`?
