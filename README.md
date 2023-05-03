Download Link: https://assignmentchef.com/product/solved-cs112-problem-set-6
<br>
<strong>Problem Set 6</strong>

<strong>Binary Search Tree (BST)</strong>

<ol>

 <li>Given the following sequence of integers:</li>

</ol>

10, 17, 3, 90, 22, 7, 40, 15

<ol>

 <li>Starting with an empty binary search tree, insert this sequence of integers one at a time into this tree. Show the final tree. Assume that the tree will not keep any duplicates. This means when a new item is attempted to be inserted, it will not be inserted if it already exists in the tree.</li>

 <li>How many item-to-item comparisons in all did it take to build this tree? (Assume one comparison for equality check, and another to branch left or right.)</li>

</ol>

<ol start="2">

 <li>For the tree built in the above problem:

  <ol>

   <li>What is the worst case number of comparisons for a successful search in this tree? For an unsuccessful (failed) search? (Assume one comparison for equality check, and another to branch left or right.)</li>

   <li>What is the average case number of comparisons for a successful search in this tree?</li>

   <li>From this tree, delete 17: find the node (y) that has the smallest value in its right subtree, write y’s value over 17, and delete y. How much work in all (locating 17, then locating y , then deleting y) did it take to complete the deletion? Assume the following (a) you are using two pointers to navigate down the tree, a tracking pointer, and a lagging pointer, (b) 1 unit of work for an equality comparison between target and tree item, one for an inequality check to branch left or right, and 1 unit of work for a pointer assignment.</li>

  </ol></li>

 <li>Given the following BST node class:</li>

</ol>

public class BSTNode&lt;T extends Comparable&lt;T&gt;&gt; {

T data;

BSTNode&lt;T&gt; left, right;         public BSTNode(T data) {             this.data = data;             this.left = null;             this.right = null;

}

public String toString() {             return data.toString();

}    }

Consider the following method to insert an item into a BST that does not allow duplicate keys:

public class BST&lt;T extends Comparable&lt;T&gt;&gt; {

BSTNode&lt;T&gt; root;         int size;

…         public void insert(T target)          throws IllegalArgumentException {




BSTNode ptr=root, prev=null;                 int c=0;

while (ptr != null) {

c = target.compareTo(ptr.data);                         if (c == 0) {

throw new IllegalArgumentException(“Duplicate key”);

}                         prev = ptr;

ptr = c &lt; 0 ? ptr.left : ptr.right;                 }

BSTNode tmp = new BSTNode(target);                 size++;

if (root == null) {                         root = tmp;                         return;

}                 if (c &lt; 0) {

prev.left = tmp;

} else {

prev.right = tmp;

}         }

Write a recursive version of this method, using a helper method if necessary.

<ol start="4">

 <li><strong>*</strong> With the same <strong>BSTNode</strong> class as in the previous problem, write a method to count all entries in the tree whose keys are in a given range of values. Your implementation should make as few data comparisons as possible.</li>

</ol>




// Accumulates, in a given array list, all entries in a BST whose keys are in a given range,     // including both ends of the range – i.e. all entries x such that min &lt;= x &lt;= max.      // The accumulation array list, result, will be filled with node data entries that make the cut.

// The array list is already created (initially empty) when this method is first called.

public static &lt;T extends Comparable&lt;T&gt;&gt;

void keysInRange(BSTNode&lt;T&gt; root, T min, T max, ArrayList&lt;T&gt; result) {

/* COMPLETE THIS METHOD */




}

<ol start="5">

 <li>With the same <strong>BSTNode</strong> class as in the previous problem, write a method that would take a BST with keys arranged in ascending order, and “reverse” it so all the keys are in descending order. For example:</li>

</ol>

25                         25

/                         /    

10     40      —&gt;        40      10

/     /                  /      /  

2   20 30   45             45  30  20   2

/                         /     

15    35                   35     15

The modification is done in the input tree itself, NO new tree is created.

public static &lt;T extends Comparable&lt;T&gt;&gt;      void reverseKeys(BSTNode&lt;T&gt; root) {

/* COMPLETE THIS METHOD */




<ol start="6">

 <li><strong>*</strong> A binary search tree may be modified as follows: in every node, store the number of nodes in its <em>right subtree</em>. This modification is useful to answer the question: what is the <strong>k-th largest element</strong> in the binary search tree? (k=1 refers to the largest element, k=2 refers to the second largest element, etc.)</li>

</ol>

You are given the following enhanced binary search tree node implementation:




public class BSTNode&lt;T extends Comparable&lt;T&gt;&gt; {

T data;

BSTNode&lt;T&gt; left, right;

int rightSize;  // number of entries in right subtree

…

}

Implement the following <em>recursive</em> method to find the <strong>k-th largest</strong> entry in a BST:




public static &lt;T extends Comparable&lt;T&gt;&gt; T kthLargest(BSTNode&lt;T&gt; root, int k) {

/* COMPLETE THIS METHOD */

}


