# Prolog List and Arithmetic Predicates

This project contains simple Prolog predicates for calculating the mean, finding the maximum value, calculating the sum of a list, and checking whether a list has an even or odd length.

## Prolog Code

```prolog
mean(A, B, Mean) :-
    Mean is (A + B) / 2.


max_list([X], X).

max_list([H|T], Max) :-
    max_list(T, MaxT),
    Max is max(H, MaxT).


sum_list([], 0).

sum_list([H|T], Sum) :-
    sum_list(T, Rest),
    Sum is H + Rest.


even_length([]).

even_length([_, _ | T]) :-
    even_length(T).


odd_length([_ | T]) :-
    even_length(T).
```

## Examples

### 1. Calculate Mean

```prolog
?- mean(10, 20, Mean).
```

Output:

```text
Mean = 15.
```

### 2. Find Maximum

```prolog
?- max_list([3, 8, 2, 10, 5], Max).
```

Output:

```text
Max = 10.
```

### 3. Calculate Sum

```prolog
?- sum_list([1, 2, 3, 4, 5], Sum).
```

Output:

```text
Sum = 15.
```

### 4. Check Even Length

```prolog
?- even_length([1, 2, 3, 4]).
```

Output:

```text
true.
```

### 5. Check Odd Length

```prolog
?- odd_length([1, 2, 3]).
```

Output:

```text
true.
```

## Combined Example

```prolog
?- sum_list([10, 20, 30, 40], Sum),
   max_list([10, 20, 30, 40], Max),
   mean(Sum, Max, Result).
```

Output:

```text
Sum = 100,
Max = 40,
Result = 70.
```

## Predicate Summary

| Predicate | Description |
|---|---|
| `mean(A, B, Mean)` | Calculates the mean of two numbers |
| `max_list(List, Max)` | Finds the maximum value in a list |
| `sum_list(List, Sum)` | Calculates the sum of a list |
| `even_length(List)` | Checks if a list has even length |
| `odd_length(List)` | Checks if a list has odd length |

## How to Run

Save the Prolog code as:

```text
main.pl
```

Run it using SWI-Prolog:

```bash
swipl main.pl
```

Then enter queries at the Prolog prompt:

```prolog
?- sum_list([1, 2, 3, 4], Sum).
Sum = 10.
```

## Requirements

- SWI-Prolog
- Basic knowledge of Prolog

## License

This project is for educational purposes.
