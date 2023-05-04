Download Link: https://assignmentchef.com/product/solved-csci311-project-2-avl-tree
<br>
Complete Assignment 7, i.e. implement an AVL-tree (balanced BST tree, name it BST as in your Assignment 7) and implement <strong><em>insert </em></strong>member function that inserts a new item in the tree and balances the tree.

Complete Assignment 8, i.e. add member function <strong><em>remove </em></strong>that removes a node from the tree.




<ul>

 <li>Add an integer <strong><em>size </em></strong>as a data member to Tnode class; the non-default constructor of the class will initialize <strong><em>size </em></strong>to 1. This data member, <strong><em>size</em></strong>, will be stored and maintained at each node. The meaning of <strong><em>size </em></strong>at any node <em>i </em>is the total number of nodes in the subtree rooted at <em>i</em>. When the constructor is called a new node is created in the tree, and this new node is the only node in the subtree rooted at this node, so the constructor initializes <strong><em>size </em></strong>at this node to 1.</li>

</ul>

You need to update your code for <strong><em>insert </em></strong>and <strong><em>remove </em></strong>to update <strong><em>size </em></strong>on each node on the path from the root to the new node (or to the removed node); this could be something similar to how you updated <em>height</em> – update function must run in constant time (this is not a recursive function, it should take just a few basic operations).

Write the following member functions to maintain and test <strong><em>size</em></strong>:

int getSize(Tnode* cur) that returns size (think what should be size of a subtree rooted at node that is NULL, i.e. if the parameter <strong><em>cur </em></strong>is NULL.

Every test t01-t08 checks printSize.

<table width="0">

 <tbody>

  <tr>

   <td width="216">int getSize(Tnode* cur)</td>

   <td width="408">returns size of the subtree rooted at the parameter <strong><em>cur</em></strong> (think what should be size of a subtree rooted at node that is NULL, i.e. if the parameter <strong><em>cur </em></strong>is NULL)</td>

  </tr>

  <tr>

   <td width="216">void updateSize(Tnode *cur)</td>

   <td width="408">Updates the size of the subtree rooted at <strong><em>cur</em></strong>, use the <em>size </em>of left and right children</td>

  </tr>

  <tr>

   <td width="216">void printSize()void printSize(Tnode *cur)</td>

   <td width="408">Traverses the tree using in-order traversal and prints <em>size </em>at each node (same format as printing <em>height</em>) </td>

  </tr>

 </tbody>

</table>




<ul>

 <li>. Implement the following member functions for AVL tree.</li>

 <li>Please watch the videos below (one is enough to implement this problem: the first a bit more complicated than the second approach). Both approaches are very useful for solving problems on a programming exam.</li>

</ul>

<u><a href="https://youtu.be/oIPxpuZ_4b0">YouTube video Find LCA using collecting paths by Elena</a></u> (15 min)

<u><a href="https://youtu.be/p-RYLDy_zZw">YouTube video Find LCA using find approach by Elena</a></u> (5 min)

<em>Definition:</em> Given two keys, <em>akey1 </em>and <em>akey2</em>, of the two nodes in AVL tree, the <em>lowest common ancestor </em>is the node in AVL tree that occurs on the path from the root to each node and whose depth is the greatest (the depth of a node is the number of edges from the root to that node).

Given two keys as parameters, <em>akey1 </em>and <em>akey2</em>, of the two nodes in AVL tree, write a member function <strong><em>findLCA </em></strong>for AVL class that finds and returns the lowest ancestor of the two nodes given by <em>akey1 </em>and <em>akey2</em>. Your function must be recursive and run in O(log<em>n</em>)-time. This function returns a <em>key</em>, i.e. <em>string </em>type object. If your function reaches NULL, return an empty string.

Tests to test this function: t09.




<ul>

 <li>Please watch the video below.</li>

</ul>

<u><a href="https://youtu.be/VYyOm8MfU8Y">YouTube video how to find the k</a><a href="https://youtu.be/VYyOm8MfU8Y">–</a><a href="https://youtu.be/VYyOm8MfU8Y">th smallest key in an AVL tree by Elena</a></u> (16 min).

Write a recursive member function <strong><em>findKthSmallest</em></strong> for AVL tree that finds and returns the <em>k</em>-th smallest key in AVL tree, where <em>k </em>is given as a parameter to this function. Your function must run in O(log<em>n</em>) worst-case time. Use the fact that each node stores <em>size</em>, the total number of nodes in the subtree rooted at this node. If your function reaches NULL, return an empty string. The count of keys in increasing order starts with 1 (i.e. the smallest key is 1-st).

Test t10 checks this function.

<ul>

 <li>Please watch the video below.</li>

</ul>

<u><a href="https://youtu.be/jgMUIjOTeHw">YouTube video how to print the longest path in an AVL</a><a href="https://youtu.be/jgMUIjOTeHw">–</a><a href="https://youtu.be/jgMUIjOTeHw">tree by Elena</a></u> (3 min).

Write a recursive member function <strong><em>printLongestPath</em></strong> for AVL tree that prints the longest path from the root to a deepest leaf in the tree (if there is a tie between some leaves, your function must choose the path to the leftmost, or the smallest-key, leaf). The order of printing is from the root to a leaf. You need to print only keys of the nodes.

Tests t11, t12, and t13 check this function.

(4)

Write a recursive member function(s) <strong><em>collectSubtree</em></strong> that takes an empty vector as a parameter, and at the end of this function, the vector will have all the nodes (keys) in the subtree rooted at the node whose key is <em>akey </em>in increasing order. You may write a few functions to handle this task. If <em>akey </em>is not in the tree, then the vector will be empty at the end of execution.

Test t14 checks this function.

( 5) Update your <em>main.cpp </em>file from Assignment 8 to be able to test your new member functions:

<table width="0">

 <tbody>

  <tr>

   <td width="117"><strong>Command </strong></td>

   <td width="507"><strong>Description of what to do for this command </strong></td>

  </tr>

  <tr>

   <td width="117">printSize</td>

   <td width="507">If command equals to “printSize”, then call member function <strong><em>printSize() </em></strong>Print out <strong><em>endl </em></strong>after calling this function.</td>

  </tr>

  <tr>

   <td width="117">findLCA</td>

   <td width="507">Using <em>cin,</em> read in two strings <em>akey1 </em>and <em>akey2, </em>and use them as parameters to call member function <strong><em>findLCA()</em></strong>.Use <em>cout </em>to print out the result returned, and then print out <strong><em>endl</em></strong>.</td>

  </tr>

  <tr>

   <td width="117">findKthSmallest</td>

   <td width="507">Using <em>cin,</em> read in an integer <em>k. </em>Call <strong><em>findKthSmallest</em> </strong>using <em>k </em>as a parameter to find and return the <em>k</em>-th smallest key in the tree.Use <em>cout </em>to print out the result returned, and then print out <strong><em>endl</em></strong>.</td>

  </tr>

  <tr>

   <td width="117">printLongestPath</td>

   <td width="507">Call <strong><em>printLongestPath(), </em></strong>and print out <strong><em>endl </em></strong>after calling this function.</td>

  </tr>

  <tr>

   <td width="117">collectSubtree</td>

   <td width="507">Using <em>cin</em>, read in a string <em>akey. </em>Use this as a parameter to call the member function <strong><em>collectSubtree</em></strong>. Another parameter to this function is an empty vector of strings. After this function has been executed, the vector will have keys of the nodes in the subtree rooted at the node whose key is <em>akey.</em> Write a for loop that will print out the keys (strings) from the vector (if the vector is not empty) in format&lt;key&gt;&lt;space&gt;At the end, print out <strong><em>endl.</em></strong></td>

  </tr>

 </tbody>

</table>

Test t15 checks all the functions after a node has been removed from the tree.