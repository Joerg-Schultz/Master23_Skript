# Python 2

## If / else / elif

Conditional code execution. Indentation is syntax.
Comparisons
- == same value
- The operators 'is' and 'is not' test for object identity: x is y is true if and only if x and y are the same object.
- Comparisons can be chained arbitrarily, and expressions like a < b < c

**Exercise** Condition expressions

## Loops
### For

**Exercise** Loops
- For loop
- Loop over a string
- Nested for Loop

**Exercise** run through a list of genes and report in which position there is a specific gene

Use enumerate to get the index with the element as you iterate:
```
  for index, item in enumerate(items):
    print(index, item)
```

### While
### break / continue
### else

Python also allows loop statements to have an else clause. It is executed when the loop terminates through exhaustion
of the iterable (with for) or when the condition becomes False (with while), but not when the loop is terminated by a break statement.

**Exercise** Loops
- while Loop
- break keyword
- Fix infinite Execution
- Else with Loops
- Else with Loops 2
- Continue keyword

**Exercise** rewrite the run through list code with while

**Exercise** Loops
- List Comprehension
- Nested List Comprehension

## Dictionaries

**Exercise** run through two linked lists (genes with name and species) to find the species of a specific gene

- Dictionaries are enclosed in curly braces, e.g., dct = {'key1' : "value1", 'key2' : "value2"}.
- A pair of braces creates an empty dictionary: {}.
- keys() + values() + items(
- if key in dictionary
- "bla" in dictionary

**Exercise** Data structures
- Dictionaries
- Add items from list
- Dictionaries keys() and values()
- Dictionary keys
- In keyword

**Exercise** go back to gene name and species example. Now use a hash. Find the name of the gene id 123

## Read files

- split() lines on \t
- string = string.replace("bla", "blub")
- with open() as bla: for line in bla

**Exercise** File input output

**Exercise** find all up-regulated kinases ("kinase" in element)
- find all significant up-regulated genes in `data/cor_vs_trap.csv`
  significant means the last column (i.e. padj) < 0.01
  upregulated means the third column (logfold change) > 0
    ```
    open the file
    read one line after the other
      for each line
        split it on the ","
        get the first (name), third (logfoldchange), last (padj) column
        if padj < 0.01 and logfold > 0
          add the name to a list
    print the length of list 
    ```
- find all kinases in `data/Dm_Interproscan.tsv`
  ```
  open the file
  read one line after the other
    for each line
      split on "\t"
      get the first column (name), the fourth column (database) and sixth column (description)
      if the database is Pfam and the description contains the word 'kinase'
        add the name to a list
  print the length of the list
    ```
- now combine these two to count all up-regulated kinases
