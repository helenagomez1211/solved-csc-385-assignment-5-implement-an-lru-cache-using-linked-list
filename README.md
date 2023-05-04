Download Link: https://assignmentchef.com/product/solved-csc-385-assignment-5-implement-an-lru-cache-using-linked-list
<br>
<strong>Instructions</strong><strong> </strong>

When accessing a large amount of data from a slow medium such as disk or network, a common speed up technique is to keep a smaller amount of data into a more accessible location known as <strong>cache</strong>. LRU (Least Recently Used cache is a widely used cache algorithm for memory management). For example, a database   system may keep data cached in memory so that it doesn’t have to read the hard drive. Or a web browser might keep a cache of web pages on the local machine so that it doesn’t have to download them over the network.




In general, a cache is much too small to hold all the data you might possibly need, so at some point you are going to have to remove something from the cache in order to make room for new data. The goal is to retain those items that are more likely to be retrieved again soon. This requires a sensible algorithm for selecting what to remove from the cache. One simple but effective algorithm is the Least Recently Used, or LRU, algorithm. When performing LRU caching, you always throw out the data that was least recently used. TheLRU cache is  based on the idea that items that are most recently used are more likely to be used againin future.




In this assignment, you are to implement a very basic Least Recently Used (LRU) cache usingLinkedList. The  Linked list has two dummy nodes: head and tail which hold references to the beginning and endof the list,  respectively.




…

<strong>(null,null) </strong>a~ ..__ … B ..__ <strong>(null,null) </strong>

head                          least Recently           used most irtem ecently           tail         used item




Every node in the linked list represent a cached item which consists of a key and a value. Duplicatekeys are not  allowed in the cache. The nodes are accessed by their keys. The first node (after head) isthe node that is least  recently accessed and the last node (before tail) is the node that is mostrecently accessed. When a user  accesses a key, the node which contains that key is moved to the end of thelist (before tail).




A cache has a limited capacity. When a new entry is added to the cache it is added to the end of the list. If the cache is full, the least recently used item (the first node after head) must be discarded (removed) from the list to make room for the new entry.




I have provided the framework of the class you need to implement “LRULinkedCache.java”. This class hasthe  following attributes:




<ul>

 <li><strong>theSize</strong>: The current number of items in the cache</li>

 <li><strong>capacity: </strong>The capacity of the cache (the maximum number of items which can be stored inthe cache)</li>

 <li><strong>head</strong>: reference to the head node</li>

 <li><strong>Tail</strong>: reference to the tail node</li>

</ul>







All you need to do is implementing three parts of this class:




<ol>

 <li><strong>The nested </strong><strong>CacheNode&lt;K,V&gt; </strong><strong>class</strong>: This class encapsulates the building block of a cache node. It contains a key and value, as well as a reference to both the next and previous nodes in the list. K is a parametric (generic) type for the key and V is a parametric type for the value.</li>

</ol>




<ol start="2">

 <li><strong>LRUGet(K key): </strong>This method returns the value for a given key in the cache and moves the node which contains the key to the end of the list (because it is most recently accessed). The method returns null if there is no node with the given key.</li>

</ol>







<ol start="3">

 <li><strong>LRUPut(K key, V value)</strong>: This method adds a new node with the given key and value to the end of the list. If the cache is full, the least recently used node (the first node after head) is removed to make room for new node. <u>Since duplicate keys are not allowed, the method must first check to see if</u> <u>a node with a given key already exists in the cache and if so, it updates its value and move the node</u> <u>to the end of the list.</u></li>

</ol>










Please follow these guidelines when implementing your class:




<ol>

 <li>Do not extend any of the data structure classes or interfaces I provided in the “source code” (doing so will be more trouble than it is worth). You do not need to use any other file beyond the provided LRULinkedCache.java file.</li>

</ol>




<ol start="2">

 <li>You can add any private helper method you want; but your code will be graded based on the LRUGet and LRUPut methods.</li>

</ol>







<ol start="3">

 <li>The LRULinkedCache.java in its current form is not compiled as its missing the implementations requested above. After you add your implementations you can compile and test your class. For example, if you use the following main method:</li>

</ol>













Your program must produce the following output:




che a.fte r            calling            ROPUT ( , 5 ) :        (1 , 5 )

c.a.ch e after calling              ROPUT ( 2, 2 ) :       (1 , 5 ) , (2, 2 ) cache after        calling I.ROPUT ( 3 , 7 ) :                ( 1 , 5 ) , ( 2 , 2 ) , ( 3 , 7 ) ca.c e a.fte r      calling I.ROPUT ( -4 , 9 ) :       ( 1 , 5 ) , ( 2 , 2 ) , ( 3 , 7 ) , ( -4 , 9 } cac_ e a.fte r            ca.lling I.ROPU’.f (1 , 9 ) :        (2, 2 ) , (3, 7 ) , (-4, 9 ) , (1 , 9 )

RUGE         (3 ) r et •Jr-ned : 7

c.ach e a.fte r                   calling                  ROGET (3 ) : (2, 2 ),, (-4, 9 ) , (1 , 9 ),, (3, 7 )

c.a.che a.fte r        c.a lli g     ROPUT (5, 10 ) :      (-4, 9 ) , (1 , 9 ) , (3, 7 ) , (5, 0) I.ROGET ( -4 ) r et , Jr-ned : 9

cache a.fte r calling ROGet (-4 ) : (1 , 9 ) , (3, 7) , (5, 1 0 ) , (-4, 9 )  ca.che a.fte r calling I.ROGet ( 0) : (1 , 9 ) , (3, 7 ) , (5, 0) , (-4, 9 )

Notice when LRUPput(1,9) is called, since a node with key=1 already exists in the cache, its value is updated to 9 and the node (1,9) is moved to the end of the list. When LRUGet(3) is called the value for key=3 is returned and the node (3,7) is moved to the end of the list.




When LRUPut(5,10) is called the cache has reached its capacity, so the least recently used node (2,2) is removed from the cache and (5,10) is added to the end of the list. When LRUGet(10) is called the cache is remained unchanged as there is no node with key=10 in the cache.




<strong>What you need to turn in: </strong>

<strong> </strong>

<ol>

 <li>Turn in your LRULinkedCache.java containing the implementations described aboveIn addition, you should submit an extra document explaining (Big-Oh) the time efficiency of the LRUPut and LRUGet method.</li>

</ol>




<strong>Grading Rubric </strong>

<strong> </strong>

<table width="640">

 <tbody>

  <tr>

   <td width="321">CacheNode&lt;K,V&gt; inner class</td>

   <td width="319">3</td>

  </tr>

  <tr>

   <td width="321">LRUGet(K key) method</td>

   <td width="319">7</td>

  </tr>

  <tr>

   <td width="321">LRUPut(K key, V value) method</td>

   <td width="319">7</td>

  </tr>

  <tr>

   <td width="321">Explaining the time efficiency of LRUPut and LRUGet methods</td>

   <td width="319"> <strong> </strong>3</td>

  </tr>

  <tr>

   <td width="321"><strong>Total: </strong></td>

   <td width="319"><strong>20 </strong></td>

  </tr>

 </tbody>

</table>


