# Slices
{id: slices}

## Slice of an array
{id: slice-on-an-array}
{i: len}
{i: cap}

{aside}
We can use the `array[start:end]` syntax to get a slice of the array. The returned object is called a `slice` and it is a window onto the underlying array.
It has a length defined by the `start` and `end` of the slice. It also has a capacity, which is all the places in the array from the `start` of the sliced to the end of the array.
{/aside}

![](examples/slice-of-array/slice_of_array.go)
![](examples/slice-of-array/slice_of_array.out)

## Slice
{id: slice}
{i: slice}
{i: len}
{i: cap}

* You can view a slice to be just a very flexible array.
* Actually it is a slice of an array. A view on a section of the array.
* len - length
* cal - capacity

{aside}
The only difference you can see when we create a slice is that we don't explicitely say its size and we also don't put the 3 dots `...` in the square bracket.

There is also a `cap` function that returns the size of the underlying array.

We can access the elements of a slice using the postfix square-bracket notation. Just as with arrays.
{/aside}

![](examples/slice/slice.go)
![](examples/slice/slice.out)

## Change value in slice 
{id: slice-change-value}

{aside}
We can access values in a slice and change them exactly as we do with an array. After all the slice is juts a window onto some array behind the scenes.
{/aside}

![](examples/slice-change-value/slice_change_value.go)
![](examples/slice-change-value/slice_change_value.out)

## Slice Assign
{id: slice-assign}

* It is an alias to the other slice, same place in memory

{aside}
Unlike with arrays, when we assign a slice, we only assign the location of the slice in the memory. So if we change the content of one of the slices then the other one also sees the change. 
{/aside}

![](examples/slice-assign/slice_assign.go)
![](examples/slice-assign/slice_assign.out)


## Slice of a slice
{id: slice-of-slice}

{aside}
We can take a slice of a slice. It is just another, most likely smaller, window on the same array in the background.
{/aside}

![](examples/slice-of-slice/slice_of_slice.go)
![](examples/slice-of-slice/slice_of_slice.out)

* This would work on arrays as well: Slices of an array

## Append to a slice
{id: append-to-a-slice}

![](examples/append-to-slice/append_to_slice.go)
![](examples/append-to-slice/append_to_slice.out)


## Slice append
{id: slice-append}
{i: append}

![](examples/slice-append/slice_append.go)
![](examples/slice-append/slice_append.out)

* Both the actual length and the capacity grew


* [slice internals](https://blog.golang.org/go-slices-usage-and-internals)
* [append to slice](https://tour.golang.org/moretypes/15)


## Remove last element of slice (pop)
{id: slice-remove-from-the-end}
{i: pop}

![](examples/slice-remove-last/slice_remove_last_element.go)
![](examples/slice-remove-last/slice_remove_last_element.out)

* The capacity remaind the same


## Remove first element of slice (shift, pop(0))
{id: remove-first-element-of-slice}
{i: shift}

![](examples/slice-shift/slice_shift.go)
![](examples/slice-shift/slice_shift.out)


## Pre-allocate capacity for slice with make
{id: pre-allocate-capacity-for-slice}
{i: make}

![](examples/slice-pre-allocate/slice_pre_allocate.go)
![](examples/slice-pre-allocate/slice_pre_allocate.out)

## For loop in slice - iterate over slice
{id: for-loop}
{i: range}
{i: for}

![](examples/loop-on-slice/loop_on_slice.go)
![](examples/loop-on-slice/loop_on_slice.out)

## for loop on values of slice (no index)
{id: for-values}

![](examples/for-values/for_values.go)


## Merge two slices
{id: merge-two-slices}
{i: ...}

![](examples/merge-slices/merge_slices.go)
![](examples/merge-slices/merge_slices.out)


## Find element in array or slice
{id: find-element-in-slice}

![](examples/find-element-in-slice/find_element_in_slice.go)
![](examples/find-element-in-slice/find_element_in_slice.out)

## Remove element of slice
{id: slice-remove-element}

![](examples/remove-element-from-slice/remove_element_from_slice.go)
![](examples/remove-element-from-slice/remove_element_from_slice.out)

## Weird merge slices
{id: weird-merge-slices}

* When we try to remove an element in the middle but assign to a new name.
* Avoid this mess!

![](examples/weird-merge-slices/weird_merge_slices.go)
![](examples/weird-merge-slices/weird_merge_slices.out)


## Sort slice
{id: sort}
{i: sort}
{i: sort.Strings}
{i: sort.Ints}

* [sort](https://golang.org/pkg/sort/)

![](examples/sort/sort.go)
![](examples/sort/sort.out)

## Are values sorted?
{id: are-sorted}
{i: StringsAreSorted}
{i: IntsAreSorted}
{i: Float64sAreSorted}

![](examples/are-sorted/are_sorted.go)
![](examples/are-sorted/are_sorted.out)


## Sort strings by length
{id: sort-strings-by-length}

![](examples/sort-by-length/sort_by_length.go)
![](examples/sort-by-length/sort_by_length.out)

## Sort strings by length and then abc order
{id: sort-strings-by-length-and-then-abc-order}

![](examples/sort-two-conditions/sort_by_two_conditions.go)
![](examples/sort-two-conditions/sort_by_two_conditions.out)

## Search in slice
{id: search-in-slice}

![](examples/search-in-slice/search_in_slice.go)
![](examples/search-in-slice/search_in_slice.out)

## Variadic function (arbitrary number of parameters)
{id: variadic-function}

* Unknown number of parameters
* The function receives a `slice` containinig the values.
* [variadic functions](https://medium.com/rungo/variadic-function-in-go-5d9b23f4c01a)

![](examples/function-sum/sum_function.go)
![](examples/function-sum/sum_function.out)

## Defer and slice
{id: defer-and-slice}

![](examples/defer-and-slice/defer_and_slice.go)


## Exercise: count words
{id: exercise-count-words-slices}

* Count how many times each word appears in a given slice
* You can use this skeleton:

![](examples/count-words-in-slices-skeleton/count_words_in_slices_skeleton.go)

* Expected output:

![](examples/count-words-in-slices/count_words_in_slices.out)


## Exercise: Create a list of words from sentences
{id: exercise-create-list}

* Given a list of strings with words separated by spaces, create a single list of all the words.

![](examples/words-from-sentences-skeleton/words_from_sentences_skeleton.go)

## Exercise: Create a unique list of values
{id: exercise-unique-values}

Given a list of strings, create a list of unique values sorted by abc.

![](examples/unique-values-skeleton/unique_values_skeleton.go)

## Exercise: Reverse Polish Calculator
{id: exercise-reverse-polish-calculator}

* Implement a reverse polish calculator.

Examples:

```
go run rpc.go "2 7 + =" 
9
```

```
go run rpc.go "2.1 7.2 - =" 
-5.1
```

```
go run rpc.go "7 2 / =" 
3.5
```

```
go run rpc.go "2 3 5 + * ="
16
```

## Exercise: DNA Sequencing
{id: exercise-dna-sequencing}

* A, C, T, G are called bases or nucleotides
* Given a sequence like "ACCGXXCXXGTTACTGGGCXTTGT" (nucleoids mixed up with other elements) return the sequences containing only ACTG orderd by length.
* The above string can be split up to ["ACCG", "C", "GTTACTGGGC", "TTGT"] and then it can be sorted to get the following:
* Expected result: ["GTTACTGGGC", "ACCG", "TTGT", "C"]


## Solution: count words
{id: solution-count-words-slices}

![](examples/count-words-in-slices/count_words_in_slices.go)

## Solution: Create a list of words from sentences
{id: solution-create-list}

![](examples/words-from-sentences/words_from_sentences.go)
![](examples/words-from-sentences/words_from_sentences.out)

## Solution: Create a unique list of values
{id: solution-unique-values}

![](examples/unique-values/unique_values.go)
![](examples/unique-values/unique_values.out)

## Solution: Reverse Polish Calculator
{id: solution-reverse-polish-calculator}

![](examples/rpc/rpc.go)

## Solution: DNA Sequencing
{id: solution-dna-sequencing}

![](examples/dna-sequencing/dna_sequencing.go)
![](examples/dna-sequencing/dna_sequencing.out)

## Solution: DNA Sequencing with in place filter
{id: solution-dna-sequencing-in-place-filter}

![](examples/dna-sequencing-in-place-filter/dna_sequencing_in_place_filter.go)
![](examples/dna-sequencing-in-place-filter/dna_sequencing_in_place_filter.out)
