---
name: "SOFTSPEC: Define"
description: Define - create what you want to build specification file.
category: Workflow
tags: [workflow, artifacts, experimental]
---

Define - create what you want to build definition file.

I'll create a change with artifact:
- definition.md (what & why)

---

**Input**: The argument after `/softspec:define` is the change name (kebab-case), OR a description of what the user wants to build.

**Steps**

1. **If no input provided, ask what they want to build**

   Use the **AskUserQuestion tool** (open-ended, no preset options) to ask:
   > "What change do you want to work on? Describe what you want to build or fix."

   From their description, derive a kebab-case name (e.g., "add user authentication" → `add-user-auth`) with max 3 word.

   **IMPORTANT**: Do NOT proceed without understanding what the user wants to build.

2. **Create the change directory**
   ```bash
   mkdir softspec/changes/<name>
   ```
   This creates a scaffolded change at `softspec/changes/<name>/`. For example if change name is `add-user-auth`; directory path will be `softspec/changes/add-user-auth`

3. **Create definition.md file**
   Create a file named `definition.md` under the change file. For example is change name is `add-user-auth`; file path will be `softspec/changes/add-user-auth/definition.md`
   In this file write a change definition with user provided info. Use this template:
   ```
   # Softspec Definion File

   ## Change Name
   write the change name here.

   ## Summary
   write a definition summary here.

   ## Details
   write all details about the change.

   ```

4. **Update state.md file**
   Update `softspec/state.json` file with change name and status 'defined'. If this file not exist; create it with content below:
   ```
   {
      "current-change": {
         "name": "add-dump-executiontime",
         "status": "defined"
      }
   }
   ```

4. **Guiding user**
   Guide user to review definition file. And it he thinks something is missing, he need to update file manually or with ai.
   Guide user to next step. User can move next step with `/softspec:plan`