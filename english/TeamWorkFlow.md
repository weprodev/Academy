# How We Work Together: A Team Workflow Guide

This page outlines our collaborative approach to teamwork. By following this workflow, we ensure efficient and effective project execution.

# Workflow 

## Step 1
1. Ensure you have access to the team's shared project board. This board outlines all tasks related to your current activities.
2. Clone the specific repository associated with the project you'll be working on.

## Step 2 - Board explanation
We conclude our weekly work period on Sunday afternoon. This weekly cycle forms the basis of our sprint and planning.

**Task Board Columns**
Our team board utilizes the following columns to track task status:

1. Backlog: A repository for all upcoming projects, features, and tasks.
2. To Do: Tasks that are ready to be started but haven't yet, we define all tasks in this column every Sunday.
3. In Progress: Tasks that are currently being worked on.
4. To Verify: Tasks that are completed and awaiting review or testing.
   1. **Task Owner Action:** Once a task is complete, the owner should unassign themselves from the task and move it to the "To Verify" column. It means, it's ready to be reviewed.
   2. **Reviewer Selection:** At least two developers (or one if there are fewer than four on the team) must review the task.
   3. **Reviewer Action, Process:** Reviewers should identify unassigned tasks, claim them by assigning themselves, and then review the code, providing feedback via pull request comments. If comments are raised, the task should be reassigned to the original owner.
   4. **Task Owner, Addressing Feedback:** If comments are raised, the task owner should reclaim the task, address the feedback, and re-assign it to the reviewer.
   5. **Reviewer Action, Approval:** Once all feedback is addressed, the reviewer should approve the pull request, unassign themselves from the task, and add the `reviewed-once` label.
   6. **Task Owner, Final Approval:** Once the task receives the required number of approvals (either one or two, depending on team policy), the owner should merge the pull request to the develop branch, unassign themselves, and move the task to the `Done` column.
5. Done: Tasks that have been reviewed, tested, and are considered complete.    
   1. All the tasks in develop branch merged to `develop` branch.
   2. All team members should be unassigned from these tasks, as they represent the collective effort of the team.


## Step 3

1. If you didn't read the [Git convention](https://blog.weprodev.com/git-convention-for-consistent-and-semantic-structure-c7b0f3ac996c), read and make sure to follow that.
2. For each change or new feature, create a corresponding task or ticket on the project board.
3. Since you've cloned the project, switch to the `develop` branch and pull the latest changes from the repository.
    `git fetch -all` or `git pull origin develop`
4. Create a new branch based on the develop branch:
    `git checkout -b [BRANCH-NAME]` like: BC1-16-Base-Structure, BC1-16 is the task Id.
5. When you have implemented all changes based on the task, add, commit and push it based on the Git Convention policies.

