Stashing Changes and Retrieving Stashed Changes :





PS D:\The GYM git Exercises\Git Advanced Exercise3> git stash
Saved working directory and index state WIP on main: 1903682 initial commit


PS D:\The GYM git Exercises\Git Advanced Exercise3> git stash      
Saved working directory and index state WIP on main: 1903682 initial commit
PS D:\The GYM git Exercises\Git Advanced Exercise3> git stash pop
   On branch main
    Your branch is up to date with 'origin/main'.

  Changes not staged for commit:
  (use "git restore <file>..." to discard changes in working directory)
        modified:   firstFile

   no changes added to commit (use "git add" and/or "git commit -a")
   Dropped refs/stash@{0} (1a17011e917759a91bbcaa6dbea6f1630798f9d0)
PS D:\The GYM git Exercises\Git Advanced Exercise3> git stash apply  
   No stash entries found.



Branch Merging Conflicts (Continued):




   
gymuruhimbi@uruhimbis-iMac squashing % echo 'Line 1: Hello World' > conflict.txt
gymuruhimbi@uruhimbis-iMac squashing % git add conflict.txt
gymuruhimbi@uruhimbis-iMac squashing % git commit -m 'Initial commit on main'
[main 988f738] Initial commit on main
 Committer: Gym Uruhimbi <gymuruhimbi@uruhimbis-iMac.local>
 create mode 100644 conflict.txt
 
gymuruhimbi@uruhimbis-iMac squashing % git checkout -b feature1-branch
Switched to a new branch 'feature1-branch'

gymuruhimbi@uruhimbis-iMac squashing % echo 'Line 1: Hello from feature branch' > conflict.txt
gymuruhimbi@uruhimbis-iMac squashing % git commit -am 'Modified conflict.txt on feature1 branch'
[feature1-branch f8d1c5b] Modified conflict.txt on feature1 branch


gymuruhimbi@uruhimbis-iMac squashing % echo 'line 1: Hello from main branch' > conflict.txt
gymuruhimbi@uruhimbis-iMac squashing % git commit -am 'Modified conflict.txt on main branch'
[main de7ee12] Modified conflict.txt on main branch


gymuruhimbi@uruhimbis-iMac squashing % git merge feature1-branch

Auto-merging conflict.txt
CONFLICT (content): Merge conflict in conflict.txt
Automatic merge failed; fix conflicts and then commit the result.

gymuruhimbi@uruhimbis-iMac squashing % git add conflict.txt
gymuruhimbi@uruhimbis-iMac squashing % git commit -m 'Resolved merge conflict in conflict.txt'


[main 4a5004e] Resolved merge conflict in conflict.txt
 Committer: Gym Uruhimbi <gymuruhimbi@uruhimbis-iMac.local>
