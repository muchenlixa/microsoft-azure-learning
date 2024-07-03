## Understand data factory control flow

### What is control flow

Control flow is an orchestration of pipeline activities that includes chaining activities in a sequence, branching, defining parameters at the pipeline level, and passing arguments while invoking the pipeline on demand or from a trigger.

Control flow can also include looping containers, that can pass information for each iteration of the looping container.

If a For Each loop is used as a control flow activity, Azure Data Factory can start multiple activities in parallel using this approach. This allows you to build complex and iterative processing logic within the pipelines you create with Azure Data Factory, which supports the creation of diverse data integration patterns such as building a modern data warehouse.

Some of the common control flow activities are described in the below sections.

### Chaining activities

With ADF, you can chain activities in a sequence within a pipeline. It's possible to use the dependsOn property in an activity definition to chain it with an upstream activity. 

### Branching activities

Use ADF for branching activities within a pipeline. Example: the IF-condition activity. A branching activity evaluates a set of activities, and when the condition evaluates to true, a set of activities are executed. When it evaluates to false, then an alternative set of activities is executed.

### Parameters

You can define parameters at the pipeline level and pass arguments while you're invoking the pipeline on-demand or from a trigger. Activities then consume the arguments held in a parameter as they are passed to the pipeline.

### Looping containers

The looping containers umbrella of control flow such as the ForEach activity defines repetition in a pipeline. It enables you to iterate over a collection and runs specified activities in the defined loop. It works similarly to the 'for each looping structure' used in programming languages. Besides each activity, there is also an Until activity. This functionality is similar to a do-until loop used in programming. What it does is running a set of activities (do) in a loop until the condition (until) is met.

### Trigger-based flows

Pipelines can be triggered by on-demand (event-based, for example, blob post) or wall-clock time.

### Invoke a pipeline from another pipeline

The Execute Pipeline activity with Azure Data Factory allows a Data Factory pipeline to invoke another pipeline.

### Delta flows

Use-cases related to using delta flows are delta loads. Delta loads in ETL patterns will only load data that has changed since a previous iteration of a pipeline. Capabilities such as lookup activity, and flexible scheduling helps handling delta load jobs. In the case of using a Lookup activity, it will read or look up a record or table name value from any external source. This output can further be referenced by succeeding activities.

## Debug data factory pipelines

In ADF, there's no need to publish changes in the pipeline or activities before you want to debug. This is helpful in a scenario where you want to test the changes and see if it works as expected before you actually save and publish them. 

A debug run allows you to do just one part of the pipeline not the whole process. You can test the pipeline end to end or set a breakpoint. By doing so in debug mode, you can interactively see the results of each step while you build and debug your pipeline. 

Be aware that by selecting the debug slider, it will actually run the pipeline itself. If the pipeline contains, for example, a copy activity, the test run will copy data from source to destination. So the best practice is to use test folders in your copy activities and other activities when debugging, such that when you are satisfied with the results and have debugged the pipeline, you switch to the actual folders for your normal operations. 