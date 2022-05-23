## 1-Click Child-Links ##

<a href="https://marketplace.visualstudio.com/items?itemName=ruifig.vsts-work-item-one-click-child-links" target="_blank">1-Click Child-Links</a> is an Azure DevOps extension for creating multiple work items as children via single click, where each work item is based on a single pre-defined template.

Azure DevOps offers team-specific work item templating as <a href="https://docs.microsoft.com/en-us/azure/devops/boards/backlogs/work-item-template?view=azure-devops&tabs=browser" target="_blank">core functionality</a> with which you can quickly apply pre-populated values for your team's commonly used fields per work item type.

The child work items created by this extension are based on the hierarchy of work item types defined in the process template (<a href="https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/agile-process-workflow?view=azure-devops" target="_blank">Agile</a>, <a href="https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/scrum-process-workflow?view=azure-devops" target="_blank">Scrum</a>, <a href="https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/cmmi-process-workflow?view=azure-devops" target="_blank">CMMI</a>).

For example, if you're using a process inherited from the agile template with a custom requirement-level type called defect and 3 task templates defined, using 1-click on a user story or defect will generate three child tasks, one for each defined template.

Put a minified (single line) JSON string into the child template's description field, like this:

``` json
{
    "applywhen": 
    {
        "System.State": "Approved",
        "System.Tags" : ["Blah", "ClickMe"],
        "System.WorkItemType": "Product Backlog Item"
    }
}
```

### Define team templates ###

<a href="https://docs.microsoft.com/en-us/azure/devops/boards/backlogs/work-item-template?view=azure-devops&tabs=browser#manage" target="_blank">Manage work item templates</a>

<img src="src/img/screen01.png" alt="Define team templates" />

### Create / open a work item ###

Find 1-Click Child-Links on toolbar menu

<img src="src/img/screen02.png" alt="1-Click Child-Links on work item form menu"/>

### Done ###

You should now have children associated with the open work item.

<img src="src/img/screen03.png" alt="Done"/>

## Release notes ##

* v1.0.0: Tags are being transferred to child tasks
* v1.1.0: Duplicate tasks are not being created (based on title)

## Usage ##
Create a new version by running:
```npx tfx-cli extension create --output-path ..\dist```


