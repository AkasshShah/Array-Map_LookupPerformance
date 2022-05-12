# Simple Benchmarking
This repo is here to do a simple benchmarking of looking up in Maps & Arrays and analyzing if something is worth it.

## Scenarios
Here we will be testing particular scenarios that appeared in real-world problems that there was a discussion about. Is it really worth using a Map/Dictionary/UnorderedMap over a simple Array/List/Vector in this particualar case?

Here the objects/structs mentioned can be as simple as
```json
{
  "name": "somethingUnique",
  "pointer": "hashToAnotherPointer(CanBeDuplicateInArray)"
}
```

### Scenario 1
A function recieves an array of objects that have certain (arbitrary) properties and we must find a certain object within the array that has a property that matches another input parameter. In this scenario, the array that is passed in may not be the same array being passed into the function over and over, hence it cannot be cached outside the scope of the function.

### Scenario 2
A function recieves an array of objects that have certain (arbitrary) properties and we must find a certain object within the array that has a property that matches another input parameter. In this scenario, the array that is passed in will be the same array being passed into the function over and over, hence it can be cached outside the scope of the function (scoping only a Map makes sense, not so much an array).

## Benchmarking
Here, we will use a similar technique for benchmarking as used in [this Prime Sieve benchmarking repository](https://github.com/PlummersSoftwareLLC/Primes).
We will initiate a particualr function as many times as possible withing a certain time window, and mark the duration of time between the first call and the end of the last execution.
For this use case, it also makes sense to benchmark the functions with a variety of differnt sized arrays.
We will always benchmark the worst-case-scenario, where the item we want to find is always in the last position we look at.