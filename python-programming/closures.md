# Closures
{id: closures}

## Counter closure
{id: counter-closure}
{i: nonlocal}

![](examples/closures/counter.py)
![](examples/closures/counter.out)


## Create incrementors
{id: creat-incrementors}

In order to use in various map-expressions, we need a couple of
function that - for simplicity - need to increment a number:

![](examples/closures/create_incrementors.py)


## Make incrementor with def (closure)
{id: make-incrementor-def}
{i: closure}
![](examples/closures/make_incrementor_def.py)


## Make incrementor with lambda
{id: make-incrementor-lambda}
![](examples/closures/make_incrementor.py)

## Exercise: closure bank
{id: exercise-closure-bank}

* Create a closure that returns a function that holds a number (like a bank account) that can be incremented or decremented as follows:
* Allow for an extra paramter called `prev` that defaults to `False`. If `True` is passed then instead of returning the new balance, return the old balance.

```
bank = create_bank(20)

print(bank())    # 20
print(bank(7))   # 27
print(bank())    # 27
print(bank(-3))  # 24
print(bank())    # 24


print(bank(10, prev=True))   # 24
print(bank())    # 34

```


## Solution: closure bank
{id: solution-closure-bank}

![](examples/closures/bank.py)