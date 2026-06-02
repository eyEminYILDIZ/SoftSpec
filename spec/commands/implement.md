---
name: "SOFTSPEC: Implement"
description: Implement - implement the previously created tasks in plan.md file.
category: Workflow
tags: [workflow, artifacts, experimental]
---

Implement - implement the previously created tasks in plan.md file.

---

**Input**: The argument after `/softspec:implement` is optional, if provided take into account.

**Steps**

1. **Detect change name**
   Detect change name from `softspec/state.json` file. With that change name, read the change definition file `softspec/changes/change-name/plan.md` file. That file contains list of tasks. This file will be used to implementing.

2. **Implement the tasks**
    Implement each task in the task list. After each completion of a task, update plan.md file as checking task's checkbox. So this file will track progress.

3. **Update state.md file**
   Update `softspec/state.json` file with change name and status 'implemented'. If this file not exist; create it with content below:
   ```
   {
      "current-change": {
         "name": "add-dump-executiontime",
         "status": "implemented"
      }
   }
   ```

4. **Output On Completion**

```
## Implementation Complete

**Change:** <change-name>
**Progress:** 7/7 tasks complete ✓

### Completed This Session
- [x] T-01 Task 1
- [x] T-02 Task 2
...

All tasks complete! Verify everything is running ok. Don't forget to check changed files manually.
```