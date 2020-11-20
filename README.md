# Day 5: Data Structure Quiz

In this quiz we'll present different programming scenarios that can be solved with several different data structures. Your job will be to choose the best one for the job based on the requirements! Pull from your Big O knowledge! Assume all answer options are valid choices (no trick questions), and that all of the necessary information about the scenario has been presented to you.

1. Mult choice

Our business handles online orders on a first-come-first-serve basis, just like a queue at the checkout of a brick-and-mortar store. We get a lot of orders and every time we go to remove one from the queue, the system responds really slowly. Adding new orders usually happens pretty quickly though. We rarely search for a specific order from a customer.

What should we do? How should we implement the Queue class that holds all of the orders? 

- Use a Linked List that tracks both its head Node and tail Node as the underlying data structure
  - Whoa! Look at you go! The business stated that they rarely search for a specific order, and that they process them in the order they come in. Mostly, orders are removed from the front of the Queue and added to the end of the Queue. This means we should optimize for fast insertion at the rear and fast removal from the front. If we track both the head and tail of the Linked List, we'll get constant time insertion at at the rear and constant time removal at the front!
- Use an Array as the underlying data structure
  - Not quite. The business stated that they get a lot of orders, so they need to optimize for adding orders to the rear of the queue and removing them from the front. Calling <code>shift</code> on an Array is a linear time procedure. Adding orders to the rear is constant time, except for when the Array must be moved in memory - then it's linear time. There's a less timely solution here.
- Use a Hash as the underlying data structure
  - Not quite. The business cares about the order in which the orders arrive. A Hash is not a good data structure to choose when order matters.
- I don't know
  - Keep on studying. With time and practice, it'll start to sink in.

2. Mult choice

We need to write an algorithm that returns `true` if there are any repeating elements in the input Array and `false` otherwise.

<pre>
<code>
Input: [1, 2, 3]
Output: false

Input: [1, 2, 1]
Output: true
</code>
</pre>

Here is our pseudocode solution:

<pre>
<code>
function hasRepeating(array):
  initialize variable seen

  iterate over array:
    if element in seen:
      return true
    
    add element to seen

  return false
</code>
</pre>

Which data structure should we use for the variable called <code>seen</code>?

- Set
  - Yes! A Set stores only unique values and has O(1) lookup time. This will make it really fast to check if the element has already been seen.
- Array
  - Not quite. There's a faster choice here. Finding the element in an Array will take O(n) linear time in the worst case, since we have to iterate over the entire Array every time we check if a value has been seen or not.
- Linked List
  - Not quite. There's a faster choice here. Finding the element in a Linked List will take O(n) linear time in the worst case, since we have to iterate over the entire list every time we check if a value has been seen or not.
- I don't know
  - Keep on studying. With time and practice, it'll start to sink in.

3. Mult choice

We are writing an algorithm to find the most frequently occurring String in an Array of Strings.

<pre>
<code>
Input: ['cat', 'dog', 'bat', 'cat', 'dog', 'cat']
Output: 'cat'
</code>
</pre>

Here is our pseudocode:

<pre>
<code>
function findMostFrequentString(array):
  initialize variable string_frequencies

  iterate over array:
    if string not in string_frequencies:
      add string to string_frequencies with count of 1
    else:
      increment count for string in string_frequencies by 1

  most_frequent = find string with highest count in string_frequencies
  return most_frequent
</code>
</pre>

Which data structure should we use for <code>string_frequencies</code>?

- Hash
  - Perfect! A Hash allows for constant time access using keys. In this case, the string will be the key and the count will be the value. This will make incrementing the counts very fast!
- 2-dimensional Array
  - Not quite. We could use a 2-dimensional Array where each string is stored in its own Array alongside a count (<code>[["cat", 1], ["dog", 3]]</code>), but that would mean that every time we go to increment the count for a String, we'd be performing a linear-time operation.
- I don't know
  - Keep on studying. With time and practice, it'll start to sink in.
