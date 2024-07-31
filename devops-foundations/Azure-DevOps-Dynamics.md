## Azure DevOps Board templates

By default, there are four templates you can choose from:
- basic
- agile
- scrum
- CMMI
Most Business Central projects will be based on the Basic, Agile, or Scrum template. CMMI template is for projects that require a framework for process improvement and an auditable record of decisions.

### Basic template

The Basic template is the easiest template. It's flexible for any process and ideal for teams starting with Azure DevOps. There isn't many levels in the work items. With the Basic template you can create three types of work items:

**Epic** decribes a large piece of work. It can be used to group different issues that all belong to the same business unit. For example, you can create an Epic to enhance and expand functionality in Business Central. The different changes will be created as **issue**. The lowest level in the template work items are **Tasks**. A task is an action that can be developed in a small amount of time. What the exact definition of a small amount time is, is something you need to discuss within your development team. Sometimes teams make the agreement that if a task takes eight hours or longer to complete, your task is defined as too wide. In this case, you can split your task inot smaller tasks that are easier to work on as a developer. 

### Agile template

Ideal for teams uing an angile planning methodology, including scrum. six types of work items:
- Epic
- Feature
- User Story
- Issue
- Bug
- Task

The Epic work item is just like the basic template in that it's used to group other work items. In the agile template, it can group features. Within the Epic, you can have a Feature that requires to extend functionality. The Feature describes what will be released with the product. Within a Feature, you can define User Stories, Issues, and Bugs. You can compare them with Issues from the basic template. The user story is there to create something new in the application, an Issue describes an obstacle in the application, and a Bug is a problem that needs to be worked on. They are all on the same level. It just depends which type of development is needed. 

It's also useful to have a better overview when you split them in one of those three work items. Then you can see all bugs in one overview, without the work items that create new functionality. The lowest level is the Task that describes the work that a developer must do. It's also on the level of the Task that the amount of work is planned and registered. 


### Scrum template

The Scrum template is targeted at teams that follow the Scrum framework. It's comparable with the Agile template, but the work items are using the naming conventions from the Scrum framework. Six types of work items:
- Epic
- Feature
- Product Backlog Item
- Impediment
- Bug
- Task

### Configure iterations

If we look back at how software was developed 10 years ago, you had a specific add-on you wanted to develop, and the add-on was only released when all features were developed. This process could take years. These days, software development is shifting to shorter development and release cycles. A typical development cycle could be as short as two weeks. After that two weeks, you can create a test release and deliver it to the customer. 

Cycles can be a bit longer or a bit shorter, but we work in cycles. Not all features will be immediately available for the customer, but it will be easier to plan the release of a specific feature. Agile and Scrum is working this way, and the Basic teamplates support the usage of cycles or Iterations. 

If we look at Scrum, there's a user that has the role of Product Owner. This person groups all requests coming from the customers, management, salespersons, internal, and so on. The product owner creates User Story, Issue, or Bug work items, and manages all those work items and prioritizes them.

In the Work Items menu, you can register all the work items in Azure Boards under the Boards section. This is just a list with all the different work items, where you can filter on type, assigned to, state, and other fields. Whenever a new request comes in, the product owner has to create a new work item in this list. 

The work items lists has no grouping or prioritizing functionality. The next step is to prioritize the different work items, because not everything can be developed within an iteration of two weeks. So you can select the menu Backlogs in the Board section. This will again show you the work items, but tasks will be grouped under a User Story, Bug, or Issue.

Here the product owner can drag the different work items to order them. Based on the available time of the team and the iteration duration, Azure DevOps will automatically suggest which work items can be developed in which iteration. An iteration is also called a sprint. 

### Create work items

You can create work items at different places. Typically, the product owner creates new items using the work items menu in the Board section. In this list, all work items are registered without any order. Depending on the type of the selected process template, the New Work item menu displays other types. Register every requirement or bug in this list. 

In the description field, you can add the content of the work item. Here, you should describe what need to be developed. In the planning field, you can prioritize the work item by assigning a number from 1 to 3.
- 1: product can't ship without the feature
- 2: product can't ship without the feature, but it deosn't have to be addressed immediately
- 3: implementation of the feature is optional based on resources, time, and risk

On the Effort field, you can put an estimate on how long it would take to develop this feature. 

On the right side of the page, you can see another section that displays information on Deployment, Development, and Related Work. 

