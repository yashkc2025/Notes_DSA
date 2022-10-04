---
---

Below cell shows how items are declared


```python
class Item:
    pass

item1 = Item()
item1.name = "Phone"
item1.price = 100

item1.quantity = 5

#printing data types
print(type(item1))
print(type(item1.name))
print(type(item1.price))
print(type(item1.quantity))
```

    <class '__main__.Item'>
    <class 'str'>
    <class 'int'>
    <class 'int'>
    

______
Python always passes the **self** argument to a method as it cannot be 0 argument function to pass itself


```python
class Item:
    def calulate_total(self,x,y): #self always needed
        return x * y

item1 = Item()
item1.name = "Phone"
item1.price = 100

item1.quantity = 5
print(item1.calulate_total(item1.price, item1.quantity))
```

    500
    

________
**`__init__`** fuction is used to define a constructor function. Functions of type **`__x__`** are called magic functions.

`__init__` is called automatically

`self.name = name` works the same as `item1.name = "phone"`

**The argument doesn't necessarily need to be the same as self.x**


```python
class Item:
    def __init__(self, name : str, price : float, quant : int):
        self.name = name
        self.price = price
        self.quantity = quant #The argument doesn't necessarily need to be the same as self.x

    def calculate_total(self): #self always needed
        return self.quantity * self.price

item1 = Item("Phone", 100, 5)
item2 = Item("Tablet", 200, 10)

print(item1.calculate_total())


```

    500
    

__________

`def __init__(self, name, price, quant = 0):` shows that the default value of quant is 0 unless defined.

__________

The below table shows that self function can be used to pass values instead of passing them explicitly.
<table>
<tr>
<td>

```python
def calculate_total(self,x,y):
        return x * y
```

</td>
<td>

```python
def calculate_total(self):
        return self.quant * self.price
```
</td>
</tr>

</table>

___
The `assert` function is used to check if the condition is satisfied by the argument.
It raises **assertionError** if the condition is not satisfied.


```python
class Item:
    def __init__(self, name : str, price : float, quant : int):
        # Run Validation on recieved arguments
        assert price >= 0, f"Price can't be negative"
        assert quant >= 0, f"Quantity can't be negative"

        # Assign to self objects
        self.name = name
        self.price = price
        self.quantity = quant #The argument doesn't necessarily need to be the same as self.x

item1 = Item("book",-10,10) # Raises assertion error
item1 = Item("book",10,10) # Does not raises assertion error
```

____
<span style = "color:fuchsia">All the local attributes are known as instance attributes while all global attributes are known as Class attributes.</span>

The class attribute is defined just like normal variable but directly inside the class body.
____

There is a magic attribute known as **`__dict__`** that allows you to access all the attributes of the object.


```python
class Item:

    disc_rate = 10 # This is a class attribute

    def __init__(self, name : str, price : float, quant : int):
        self.name = name
        self.price = price
        self.quantity = quant 
item3 = Item("Book",300,2)

item3.disc_rate = 20 #overriding the class attribute
print(item3.disc_rate)
```
