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
    def __init__(self, name, price, quant):
        self.name = name
        self.price = price
        self.quantity = quant #The argument doesn't necessarily need to be the same as self.x

    def calulate_total(self,x,y): #self always needed
        return x * y

item1 = Item("Phone", 100, 5)
item2 = Item("Tablet", 200, 10)

print(item1.name)
print(item2.name)
print(item1.price)
print(item2.price)
print(item1.quantity)
print(item2.quantity)


```

    Phone
    Tablet
    100
    200
    5
    10
    

__________

`def __init__(self, name, price, quant = 0):` shows that the default value of quant is 0 unless defined.

__________

The below table shows that self function can be used to pass values instead of passing them explicitly.
<table>
<tr>
<td>

```python
def calulate_total(self,x,y): #self always needed
        return x * y
```

</td>
<td>

```python
def calulate_total(self): #self always needed
        return self.quant * self.price
```
</td>
</tr>

</table>
