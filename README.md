# Implementation and Visualization of Red/Black Trees
Carl Ehrett and Stephen Peele, November 29, 2016

## Nature of project 
Binary search trees (BSTs) are a structure for storing sorted data. Times to look up information, insert new entries, or delete entries are on average proportional to the log of the number of entries in the tree -- i.e., they are of average complexity O(log(n)). However, in worst case scenarios, BSTs can instead have O(n), which for large n is much slower. Red/black trees (RBTs) are a variant of BSTs with extra constraints on the structure of the tree, which guarantee that the worst-case scenarios are still O(log(n)).

## Implementation
This Jupyter notebook uses Python 2 to implement left-leaning red/black trees (Sedgwick 2008, *Left-leaning Red-Black Trees*, https://www.cs.princeton.edu/~rs/talks/LLRB/LLRB.pdf), a variant of RBTs.

## Details and Results
The RBTs implemented here are shown in the Jupyter notebook to be significantly faster than traditional BSTs for worst-case input. They are (as expected) not as fast as traditional BSTs for ordinary-case input, since RBTs involve additional computational overhead beyond what is required for simpler BSTs. For details on the background of RBTs, their implementation here, and the results obtained using this code, please see the included [report](./RBTrees.pdf).

## To use this code
Required libraries are rcParam from pylab, and pyplot from matplotlib. The RBT class is defined in section 3 of the notebook, and it depends on the class TreeNode which is a dependency for RBT() defined in section 2. Likewise, the plot_tree() function is defined in section 2, along with plot_node() upon which it depends.
### Example: create RBT
`>>>rbt = RBT()`
### Example: insert into RBT
`>>>usernames_rbt = RBT()`  
`>>>usernames_rbt.insert('Bob')`  
`>>>userids_rbt = RBT()`  
`>>>userids_rbt.insert(355)`
### Example: Look-up (check if element is in RBT)
`>>>usernames_rbt.is_element('Alice')`  
`False`  
`>>>userids_rbt.is_element(355)`  
`True`
### Example: Delete from RBT
`>>>usernames_rbt.delete('Bob')`
### Example: Plot RBT
`>>>people1 = ['Bob','Alice','Doug','Kathy','Queen','Carol','Irene','Tom',`  
`...      'Peter','Wanda','Yaakov', 'Luis','Zandra','Ronald','Mabel','Ursala','Eve',`  
`...      'Frank','Ginger','Norm','Sarah','Jeff','Vince','Howard',`  
`...      'Oprah']`  
`>>>rbt = RBT()`  
`>>>for p in people1: rbt.insert(p)`  
`...`  
`>>>plot_tree(rbt.tree)`
![RBT](./rbt.png "RBT rendered via plot_tree()")
### Example: Traverse tree in order (print all elements)
`>>>people1 = ['Bob','Alice','Doug','Kathy','Queen','Carol','Irene','Tom',`  
`...      'Peter','Wanda','Yaakov', 'Luis','Zandra','Ronald','Mabel','Ursala','Eve',`  
`...      'Frank','Ginger','Norm','Sarah','Jeff','Vince','Howard',`  
`...      'Oprah']`  
`>>>rbt = RBT()`  
`>>>for p in people1: rbt.insert(p)`  
`...`  
`>>>print(rbt.tree.traverse_infix())`  
`['Alice', 'Bob', 'Carol', 'Doug', 'Eve', 'Frank', 'Ginger', 'Howard', 'Irene', 'Jeff', 'Kathy', 'Luis', 'Mabel', 'Norm', 'Oprah','Peter', 'Queen','Ronald', 'Sarah', 'Tom', 'Ursala', 'Vince', 'Wanda', 'Yaakov', 'Zandra']`  
