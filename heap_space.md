
Analyzing Heap space for the tomcat application running on my local machine by using J Visual VM:

Need for analysis: High memory usage is still one of the most frequent problems that we see and they often have performance implications.

Analysis:

#Whenever we run any java application on our local machine we can monitor that application and we can analyze the heap space consumed by that application using the j visual vm.

#I am analyzing the tomcat application which was running on my machine.

#Initially tomcat application used a heap memory i.e about 70% of the heap size allocated by the JVM.

![jvm](https://github.com/arunkundrupu1990/jvm/blob/master/01%20Screenshot%20from%202018-08-14%2014-57-51.png)

#JVM automatically invoked garbage collection in order to clean up the heap of unreferenced or dead objects. Now my heap memory is cleared.

![jvm](https://github.com/arunkundrupu1990/jvm/blob/master/02%20Screenshot%20from%202018-08-14%2014-58-19.png)

#Whenever request comes to tomact application then heap memory of my applications increasing  and reaches the maximum limit allocated to heap memory by the JVM. Here the dynamic memory is storing in heap space. Due to this my application may runs slowly.

![jvm](https://github.com/arunkundrupu1990/jvm/blob/master/03%20Screenshot%20from%202018-08-14%2015-01-33.png)

#If the heap memory is full then grabage collector will clean up the heap of unreferenced or dead objects.

#If we used heap dump then memory allocated for heap space increased (In my case it increased upto 600MB). Also it cleans the heap memory used by the application.

 ![jvm](https://github.com/arunkundrupu1990/jvm/blob/master/04%20Screenshot%20from%202018-08-14%2015-07-43.png)

 Note:

- By default, Java has two seperate threads for Garbage collection, one for young or minor GC and the other is for older or major GC.
- The minor GC more frequently occurs to clean up garbage in the young generation. While the major GC which is less frequent cleans up the garbage of old generation.
- If the major GC too fails to free required memory, then JVM increases the current memory to help create new object.
