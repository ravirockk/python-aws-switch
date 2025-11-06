# DAY 1: PYTHON MEDIUM LEVEL - 10 CONCEPTS
# Author: Aman | AWS + Python Switch | 06 Nov 2025

# 1. List vs Tuple
print("=== 1. List vs Tuple ===")
fruits = ['apple', 'banana']
fruits.append('orange')
print("List:", fruits)

colors = ('red', 'green')
print("Tuple:", colors[0])

# 2. *args, **kwargs
print("\n=== 2. *args, **kwargs ===")
def demo(a, b, *args, **kwargs):
    print("a:", a)
    print("b:", b)
    print("args:", args)
    print("kwargs:", kwargs)

demo(1, 2, 3, 4, name="Aman", job="Dev")

# 3. Decorator
print("\n=== 3. Decorator ===")
def login_required(func):
    def wrapper(*args, **kwargs):
        if 'user' in kwargs and kwargs['user']:
            return func(*args, **kwargs)
        return "Login First!"
    return wrapper

@login_required
def dashboard(user=None):
    return f"Welcome {user}!"

print(dashboard(user="Aman"))
print(dashboard())

# 4. List Comprehension
print("\n=== 4. List Comprehension ===")
squares = [i**2 for i in range(1, 6)]
print("Squares:", squares)

# 5. Lambda + Filter
print("\n=== 5. Lambda + Filter ===")
numbers = [1, 2, 3, 4, 5, 6]
even = list(filter(lambda x: x % 2 == 0, numbers))
print("Even:", even)

# 6. __init__ vs __str__
print("\n=== 6. __init__ vs __str__ ===")
class Expense:
    def __init__(self, title, amount):
        self.title = title
        self.amount = amount
    
    def __str__(self):
        return f"{self.title}: ₹{self.amount}"

e = Expense("Lunch", 150)
print(e)

# 7. Global vs Local
print("\n=== 7. Global vs Local ===")
x = 10
def func():
    x = 20
    print("Local x:", x)
func()
print("Global x:", x)

# 8. Try-Except-Finally
print("\n=== 8. Try-Except-Finally ===")
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("Cleanup done!")

# 9. Generator
print("\n=== 9. Generator ===")
def count_up_to(n):
    i = 1
    while i <= n:
        yield i
        i += 1

for num in count_up_to(3):
    print("Yield:", num)

# 10. Dict get() vs []
print("\n=== 10. Dict get() vs [] ===")
data = {'name': 'Aman'}
# print(data['age'])  # KeyError!
print("Age with get():", data.get('age', 25))

