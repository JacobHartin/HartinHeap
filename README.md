HartinHeap
==========

Data structure that insures O(1) findMin, findMax. Supports standard heap operations (insert, merge, find) as well as findRange

TODO:

* [ ] Make children appear on same level
* [ ] Implement functions
** [ ] findRange
** [ ] removeMin
** [ ] removeMax
** [ ] merge


May also want to think about returning to original algorithm for storing max.
Max used to be stored in the child list, like a normal child, and all the max's ancestors just pointed to it.
That would allow instant RemoveMax, since max by definition could have no children.
However, you would have to go back up the heap to update the new reference, which is O(L), where L = levels of the heap.
Currently, each node's max is stored by the node itself, and is seperate from its children.

Therefore, the first node has both the min and the max, so it knows the range of all its children.

I believe removeMax should still be O(L), with every node down the right side of the tree having to pass its max up the ladder to its parent. Haven't implemented yet, so not completely sure.
