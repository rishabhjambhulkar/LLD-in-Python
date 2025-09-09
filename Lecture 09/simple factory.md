Perfect 👍 That Java code is the **Simple Factory Pattern**.
Here’s the equivalent **Python version**:

---

## 🔹 Python Code (Simple Factory)

```python
from abc import ABC, abstractmethod

# --- Burger Interface ---
class Burger(ABC):
    @abstractmethod
    def prepare(self):
        pass


# --- Concrete Burgers ---
class BasicBurger(Burger):
    def prepare(self):
        print("Preparing Basic Burger with bun, patty, and ketchup!")


class StandardBurger(Burger):
    def prepare(self):
        print("Preparing Standard Burger with bun, patty, cheese, and lettuce!")


class PremiumBurger(Burger):
    def prepare(self):
        print("Preparing Premium Burger with gourmet bun, premium patty, cheese, lettuce, and secret sauce!")


# --- Simple Factory ---
class BurgerFactory:
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


# --- Client Code ---
if __name__ == "__main__":
    burger_type = "standard"

    my_factory = BurgerFactory()
    burger = my_factory.create_burger(burger_type)

    if burger:
        burger.prepare()
```

---

## 🔹 Key Differences from Java Version

1. **Interfaces:**

   * Java uses `interface Burger` and `implements`.
   * Python uses `ABC` + `@abstractmethod` (optional, but closer to Java style).

2. **String Handling:**

   * Java: `equalsIgnoreCase("basic")`.
   * Python: `type.lower() == "basic"`.

3. **Printing:**

   * Java: `System.out.println(...)`.
   * Python: `print(...)`.

4. **Null vs None:**

   * Java: `return null;`
   * Python: `return None`.

5. **Main Execution:**

   * Java: `public static void main(String[] args)`
   * Python:

     ```python
     if __name__ == "__main__":
         ...
     ```

---

⚡ In **Simple Factory**, there’s **only one factory class** (`BurgerFactory`) that knows how to create all burger types.

👉 Compared to the **Factory Method** version you asked about earlier, here we don’t have multiple factories (`SinghBurger`, `KingBurger`) — just **one central factory**.

---

Would you like me to now put **Simple Factory vs Factory Method in Python side by side** so you can visually see the difference in code structure?
