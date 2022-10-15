# Funkcje
są to bloki kodu, które są wykonywane tylko w momencie ich wywołania  

## Przykłady
funkcja bez argumentów
```python
def hello():
    print("Hello World")

hello()
```

funkcja z jednym argumentem
```python
def say_hello(name):
    print(f"Hello {name}")

say_hello("Jan")
```

funkcja z wieloma argumentami, *positional & keyword arguments*
```python
def say_hello_to(a, b, c):
    print(f"Hello {a} {b} {c}")

say_hello_to("Edward", "Grzegorz", 5)
say_hello_to(c=5, b="Grzegorz", a="Edward")
```

funkcja z dowolną ilością argumentów
```python
def say_hello_args(*args):
    for argument in args:
        print(f"argument: {argument}")

say_hello_args(True, False, "Oskar", "Wojciech", "Andrzej")
```

funkcja zwracająca wynik
```python
def multiply(number1, number2):
    return number1 * number2

x = multiply(5,8)
```

istniejące funkcje zwracające losowe wartości
```python
import random

lista = ["raz","dwa","trzy"]
a = random.randint(5,8)
b = random.random()
c = random.choice(lista)
random.shuffle(lista)

print(lista)
```

## Definicje 📝
* https://docs.python.org/3/tutorial/controlflow.html#defining-functions

## Zadania ✏️
1. Napisz funkcję która przyjmie dwie wartości liczbowe i zwróci większą z nich
2. Napisz funkcję która przyjmie listę liczb jako argument i zwróci ich sumę
3. Napisz funkcję która przyjmie dowolnie długą listę liczb (użyj *args) i zwróci najmniejszą z nich
4. Napisz funkcję która poprosi użytkownika o podanie jego imienia, a następnie doda je do globalnej listy imion i wypisze w konsoli

**5. Napisz grę papier, kamien, nożyce.**
* w pierwszym kroku zostanie pobrana figura od użytkownika
* następnie system wylosuje wybór przeciwnika *random*
* za pomocą instrukcji warunkowej zdecyduje i wypisze kto jest zwycięzcą
* dodatkowa opcja to dodanie możliwości ponownej rozgrywki w ramach jednego uruchomienia programu