# Programowanie funkcyjne

## Funkcja wyższego rzędu 
ang. *higher order function*

1. jest to funkcja, która przyjmuje inną funkcje jako argument
```python
def shout(text): 
    return text.upper() 
    
def whisper(text): 
    return text.lower() 
    
def display(func): 
    text = func("Hello Higher Order Function") 
    print(text)
    
display(shout) 
display(whisper)
```
2. lub zwraca inną funkcję
```python
def divisor(x):
    def dividend(y):
        return y / x
    return dividend

divide = divisor(2)
print(divider(10))
```

## Lambda
są to jedno linijkowe funkcje zawierające słowo kluczowe *lambda* o formacie ```lambda parameters:expression```
```python
# without
def double(x):
    return x * 2
print(double(5))

# with
double = lambda x:x * 2
multiply = lambda x, y: x * y
print(double(5))
print(multiply(2, 3))
```

**sort** - sortuje według zadanej funkcji ```sorted(iterable,key=function)```  
```lambda data:data[1]```  

**map** - stosuje funkcję mapującą dla każdego elementu ```map(function, iterable)```  
```lambda data: (data[0],data[1]/2)```  

**filter** - filtruje kolekcje na podstawie warunku logicznego ```filter( function, iterable)```  
```lambda data:data[0] != 1```   

**reduce** - redukuje dane wejściowe do pojedynczej wartości skumulowanej, powtarza proces aż pozostanie jedna wartość ```functools.reduce(function, iterable)```  
```lambda x, y,:x + y, string_array```

## Listy składane
ang. *list comprehensions*  
```list = [expression for item in iterable]```  
```list = [expression for item in iterable if conditional]```  
```list = [expression if/else for item in iterable]```
```python
# for loop
data = []
for i in range(11):
	data.append(i)

# list comprehension
data = [i for i in range(11)]
```


## Zadania
Przygotuj *lambda function* lub *list comprehension*, która:  
1. za pomocą listy składanej wyświetl tylko liczby podzielne przez 2 dla danych ```liczby = [100, 95, 80, 75, 60, 55, 40, 35, 20, 15, 0]```  
2. przyjmuje wiek i zwróci *bool* informujący czy osobna jest pełnoletnia  
3. posortuje listę czterech dowolnych miast po ilości znaków   
4. posortuje mapę po wartościach ```gazy = {'hel': 1, 'neon': 2, 'argon': 6, 'ksenon': 8}```  
5. sprawdzi czy wszystkie liczby są typu zmiennoprzeciwnkowego ```liczby = [1.5, 5.1, 6.3, 2.2, 8.4]```  
6. znajdzie część wspólną dwóch list ```l1 = [1, 2, 3, 5, 7, 8, 9, 10]``` oraz ```l2 = [1, 2, 4, 8, 9]```
7. znajdzie tylko stringi, które są anagramami ```input = ['bcda', 'abce', 'cbda', 'cbea', 'adcb']```   
8. zamieni listę liczb całkowitych ```lista = [1, 2, 3, 4]``` na listę stringów  
9. doda do siebie trzy listy ```l1 = [1, 2, 3]```, ```l2 = [4, 5, 6]```, ```l3 = [7, 8, 9]```  
