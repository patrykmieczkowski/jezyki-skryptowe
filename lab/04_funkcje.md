# Funkcje

# Typy
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

funkcja z wieloma argumentami
```python
def say_hello_to(a, b, c):
    print(f"Hello {a} {b} {c}")

say_hello_to("Edward", "Grzegorz", 5)
```

funkcja z dowolną ilością argumentów
```python
def say_hello_args(*args):
    for argument in args:
        print(f"argument: {argument}")

say_hello_args(True, False, "Oskar", "Wojciech", "Andrzej")
```

## Definicje 📝
* https://docs.python.org/3/tutorial/controlflow.html#defining-functions

## Zadania ✏️
1. Napisz funkcję która poprosi użytkownika o jego trzy dowolne dane osobowe, a następnie przechowa je w strukturze
2. Napisz funkcję która przyjmie dwie wartości liczbowe i zwróci większą z nich
3. Napisz funkcję która przyjmie listę liczb jako argument i zwróci ich sumę
4. Napisz funkcję która przyjmie dowolnie długą listę liczb (użyj *args) i zwróci najmniejszą z nich
5. Napisz funkcję która przyjmie od użytkownika dane: imie (str), nazwisko (str), grupa (str), obecny (bool) i zapisze je do globalnej listy studentów.