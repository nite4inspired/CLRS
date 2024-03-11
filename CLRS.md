# How to Fold All or Unfold All in .md files
Fold All: Ctrl + K, Ctrl + 0 (zero)
Unfold All: Ctrl + K, Ctrl + J

# 1 The Role of Algorithms in Computing

# algorithm
a well-defined computational procedure that takes input and produces output in a finite amount of time. a tool for solving a well-specificed computational problem.

# computational problem
a problem that specifies in general terms the desired input/output relationship

# instance of a problem
an input satisfying the constraints imposed in the problem statement.

# a correct algorithm
an algorithm is correct if every problem instance halts - finishes its computing in finite time - and outputs the correct solution to the problem instance.

# data structure
a way to store and organize data in order to facilitate access and modifications.

# 1.1-1 Describe your own real-world example that requires sorting. Describe one that requires finding the shortest distance between two points.
Organizing a library; GPS navigation system

# 1.1-2 Other than speed, what other measures of effciency might you need to consider in a real-world setting?
Cost, Energy, Resource, Time, Space, Accuracy and Precision, Labor, Operational


# 1.1-3 Select a data structure that you have seen, and discuss its strengths and limitations.
Hash Tables; Strengths: Fast Access, Unique Keys, Flexible Keys, Dynamic Resizing, Direct Addressing; Limitations: Hash Collisions, Memory Overhead, Ordering, Hash Function Sensitivity, Variable Performance

# 1.1-4 How are the shortest-path and traveling-salesperson problems given above similar? How are they different?
Similarities: graph-based, optimization goals, use of weights, applicability; Differences: Problem Complexity, Scope, Circuit Requirement, Algorithmic Approaches

# 1.1-5 Suggest a real-world problem in which only the best solution will do. Then come up with one in which "approximately" the best solution is good enough.
Aircraft Design and Safety; Traffic Flow Optimization

# 1.1-6 Describe a real-world problem in which sometimes the entire input is available before you need to solve the problem, but other times the input is not entirely available in advance and arrives over time.
Scenario 1: Entire Input Available in Advance
In some cases, a business may have comprehensive data on future demand due to pre-orders, contracts, or highly predictable seasonal patterns. For example, a toy manufacturer might have detailed orders from retailers ahead of the holiday season, or a fashion retailer could have pre-season orders based on fashion trends. In these situations, the company has the entire input (demand forecast) available in advance. This allows them to optimize their inventory levels, production schedules, and supply chain logistics well before the products are needed, ensuring they meet demand efficiently without overstocking.

Scenario 2: Input Arrives Over Time
Conversely, demand can often be uncertain and change dynamically, with new information arriving over time. This is common in industries subject to rapid shifts in consumer preferences, unexpected events, or supply chain disruptions. For instance, a grocery store may not know exactly how much of a particular product will be needed week-to-week and must adjust orders frequently based on sales data, supplier availability, and current events affecting buying patterns. In these cases, the business must adapt to incoming information, constantly updating forecasts and making inventory decisions on the fly to balance the risks of stockouts against the costs of overstocking.

Solution Approaches
For the first scenario, deterministic models and optimization techniques can be applied confidently, using the full set of available data to make informed decisions. For the second scenario, more flexible and adaptive approaches are needed, such as just-in-time inventory systems, dynamic pricing models to manage demand, or machine learning algorithms that continuously update forecasts as new data arrives.

# algorithms are technology
Total system performance depends on choosing efficient algorithms as much as on choosing fast hardware.

# 1.2-1 Give an example of an application that requires algorithmic content at the application level, and discuss the function of the algorithms involved.
Search Engine: Crawling and Indexing, Query Processing, Ranking, Personalization and Context Awareness, Spam Filtering, Semantic Analysis

# 1.2-2 Suppose that for inputs of size n on a particular computer, insertion sort runs in 8n² steps and merge sort runs in 64nlogn steps. For which values of n does insertion sort beat merge sort?
n < 6.507

# 1.2-3 What is the smallest value of n such that an algorithm whose running time is 100n² runs faster than an algorithm whose running time is 2ⁿ on the same machine?
n > 14.325

# 1-1 For each function f(n) and time t in the following table, determine the largest size n of a problem that can be solved in time t, assuming that the algorithm to solve the problem takes f(n) microseconds.
too tedious

# 2 Getting Started

# keys
numbers to be sorted

# satellite data
data associated with keys

# record
key and satellite data

# pseudocode
a notation resembling a simplified programming language, used in program design.

# loop invariant
When you’re using a loop invariant, you need to show three things:
Initialization: It is true prior to the first iteration of the loop.
Maintenance: If it is true before an iteration of the loop, it remains true before the next iteration.
Termination: The loop terminates, and when it terminates, the invariant - usually along with the reason that the loop terminated - gives us a useful property that helps show that the algorithm is correct.

# 2.1-1 Using Figure 2.2 as a model, illustrate the operation of INSERTION-SORT on an array initially containing the sequence {31, 41, 59, 26, 41, 58}

# 2.1-2
At the start of each iteration of the for loop of lines 2, the variable sum is equal to the sum of the values in the subarray A[1:i-1].

# 2.1-3
for i = 2 to n
  key = A[i]
  j = i - 1
  while j > 0 and A[j] < key
    A[j + 1] = A[j]
    j = j - 1
  A[j + 1] = key

# 2.1-4
for i = 1 to n
  if x == A[i]
    return i
return NIL

loop invariant:
At the start of each iteration of the for loop of line 98, x is not found in the subarray A[1:i-1]. At the end of each iteration, either A[i] == x or x is not found in the subarray A[1:i].

Initialization:
Before the first iteration, x is not found in the subarray A[1:0] (which is an empty). After the first iteration, either x == A[1] or x is not found in the subarray A[1:1].

Maintenance:
Before the ith iteration, x is not found in the subarray A[1:i-1]. If it was found, it would've terminated beforehand. Either A[i] == x or x is not found in the subarray A[1:i].

Termination:
If x == A[i], then it returns i correctly. If it's not found from A[1:n], then it would return NIL.

# 2.1-5
ADD-BINARY-INTEGERS(A, B, n)
  carry = 0
  for i = 1 to n
    if A[i] + B[i] + carry == 0
      C[i] = 0
    else if A[i] + B[i] + carry == 1
      C[i] = 1
      carry = 0
    else if A[i] + B[i] + carry == 2
      C[i] = 0
      carry = 1
    else if A[i] + B[i] + carry == 3
      C[i] = 1
      carry = 1
  if carry == 1
    C[n+1] = 1
  return C


