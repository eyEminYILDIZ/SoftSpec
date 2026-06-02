# SoftSpec
SoftSpec is a lightweight 'Spec Driven Development' approach

## Workflow

Define => Plan => Implement

### Define

```sh
/softspec:define tell what you want to do...
```

With this command you can defined what you want, then it will create 'definition.md' file. Review this file manually after file created. Request updates if you are not happy with result.

### Plan

```sh
/softspec:plan optional additional information...
```

With this command you can create a plan and task list into 'plan.md' file under change folder. Review this file manually after file created. Request updates if you are not happy with result.


### Implement

```sh
/softspec:implement optional additional information...
```

With this command coding agent will start doing tasks in the 'plan.md' file. After implementation it will update task list by checking completed tasks. Don't forget to manually check the implementation.