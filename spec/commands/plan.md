---
name: "AIDEV: Plan"
description: Plan - create a plan and task list about the change in plan.md file.
category: Workflow
tags: [workflow, artifacts, experimental]
---

Plan - create a plan and task list about the change in `plan.md` file.

I'll create a plan and task list with artifact:
- plan.md (how)

---

**Input**: The argument after `/aidev:plan` is optional, if provided take into account.

**Steps**

1. **Detect change name**
   Detect change name from `aidev/state.json` file. With that change name, read the change definition file `aidev/changes/change-name/definition.md` file. That file contains last change request details. This file will be used to generate next file.

2. **Create plan.md file**
   Create a file named `plan.md` under the change file. For example is change name is `add-user-auth`; file path will be `aidev/changes/add-user-auth/plan.md`
   In this file write a plan and task list with checkboxes from change request in `definition.md` file that in the same directory.
   Plan must shows the end to end solution.
   Tasks must shows the solution as small chunks of changes.

   At writing `plan.md` file use this template:
   ```
   # AiDev Plan File

   ## Plan
   in this section demonstrate the end to end solution.

   ## Tasks
   write a definition summary here. Use phases if needed. Give numbers to tasks.
   [ ] T-01 Add 'remember me' checkbox on the login page
   [ ] T-02 Add rememberMe property to request model
   [ ] T-03 Update GenerateJwt() method and update jwt lifetime according to this property.
   ... so on...

   ```

3. **Update state.md file**
   Update `aidev/state.json` file with change name and status 'planned'. If this file not exist; create it with content below:
   ```
   {
      "current-change": {
         "name": "add-dump-executiontime",
         "status": "implemented"
      }
   }
   ```

4. **Guiding user**
   Guide user to review plan.md file. And it he thinks something is missing, he need to update file manually or with ai.
   Guide user to next step. User can move next step with `/aidev:implement`