##1.What is ring_queue
Queue is a common data structure, this structure ensures that the data is in accordance with the "first in first out" principle, that is, the first element is the first out of the element.Circular queue is a special queue structure , To ensure that the elements are FIFO, but the difference with the general queue is that they are circular, that is, queue head is the last element of the queue tail, usually a fixed number of elements to accommodate a closed loop.

##2.One implementation of ring_queue
###2.1Storage structure

List and linear tables are possible, but almost all with a linear table to achieve, much faster than the list, the reason is obvious, because the need to visit the list one by one traversal.

###2.2Read and write index

There are two index is very important, one is written index, marking the current element can be written index, push in queue to use. One is to read the index, marking the current element can be read the index, pop out of queue to use.

###2.3Read and write flag switching

There is a very clever way, in the queue of each element of the head plus an element marked field, marking the element is readable or writable, and the key is when to set the element can read and write state, Refer to the linux kernel implementation principle, when this element after reading, to set the writeable state, when this element is written to complete, to set the readable state.

 
##3.Test
In the CentOS 5.5 (cpu per core frequency 1200MHz) on a simple device test a bit. The size of the circular queue is 10000, the data size of the element is 4 bytes, the element that can be written and read every second is 250 million, namely 250pps


