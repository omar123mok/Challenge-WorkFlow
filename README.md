
# Workflows-Demo

A workflow helps define events which will trigger actions.


## Events
Can be of the following type:
- push
- pull_request
- release

In this demo, push type of event is used.

## Code

```yaml
name: workflow

on  : push

jobs:
  ubuntu :
    runs-on : ubuntu-latest
    steps   :
      - run : date
  windows:
    runs-on : windows-latest
    steps   :
      - run : date
  mac-os :
    runs-on : macos-latest
    steps   :
      - run : date
  custom :
    runs-on : ubuntu-latest
    needs   : [ubuntu,windows,mac-os]
    steps   :
      - run : date

```


## Screenshots

![App Screenshot](https://raw.githubusercontent.com/omar123mok/Challenge-Workflow/master/flowchart.jpg)

    Red lines indicates the jobs running parallely.
    Green line indicates dependency between the jobs.
    Dependency is achieved by using needs block.
    
    needs: [ubuntu,windows,mac-os]

    After the jobs inside needs are executed,
    the cutsom job is executed


