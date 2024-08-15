Case study
-
To cause a memory leak in the application to see how it works and then use a tool called LeakCanary by square
which automatically detects memory leaks of the following objects instances: Activity, Fragment, View, ViewModel, Service

Technologies
-
    LeakCanary

Tips/How it works?
-
How memory leak is being caused?
* An object has been declared outside a static field(Activity), then a property of this object has been set
  inside an static object being represented by SecondActivity, then when we finish this second activity the property of this companion object will hold the context of the SecondActivity that doesn't even exist anymore,
  this object should be killed as the SecondActivity however its declaration is outside a static object and it will not be killed,
  so now this object is holding an unnecessary use of memory, causing a memory leak.
  <br>

How the memory leak is being detected?
* The memory leak is being detected by the LeakCanary library which detect the memory leak when the SecondActivity is destroyed.

Sources
-
<br>
Tutorial: https://www.youtube.com/watch?v=VvkRe9vP5Oc
<br>
Documentation: https://square.github.io/leakcanary/
