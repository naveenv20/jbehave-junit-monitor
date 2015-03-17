When you run a JBehave scenario you do not get very good monitoring of your test progress.
This code will allow you to see each individual step being executed as part of your scenario, as if it were an individual test case. It is stretching the metaphor a little bit, but I personally like the results...


![http://img262.imageshack.us/img262/7229/picture2fc6.png](http://img262.imageshack.us/img262/7229/picture2fc6.png)


This code was produced to be able to sit on top of JBehave without modifying its API or internal workings at all. I'm sure if it was integrated into the API, and a few refactorings were made the solution could be a little more elegant.


For an example of how to integrate with your JBehave scenario's look at ExampleScenario in the test directory


Further work I have planned to try, is to update various JUnit runners (specifically the eclipse one) so that they can map directly to the correct step in the code. This currently does not work because the steps are not named as per the step method that is called.


PS. This code will fall over in a heap if you do not call it in a single threaded fashion.
I've made a huge assumption that most test runners are single threaded.