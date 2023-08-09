## Tips & Tricks

- Tips
    
    ## Rename a branch
    
    ```jsx
    git branch -m <new-branch-name>
    ```
    
    ## Show all tracked files
    
    ```
    git ls-files -t
    ```
    
    ## Show all untracked files
    
    ```jsx
    git ls-files --others
    ```
    
    ## Stash changes before rebasing
    
    ```jsx
    git rebase --autostash
    ```
    
    ## Undo assume-unchanged.
    
    ```jsx
    git update-index --no-assume-unchanged <file_name>
    ```
    
    ## Restore deleted file.
    
    ```
    git checkout <deleting_commit> -- <file_path>
    ```
    
    ## Restore file to a specific commit-hash
    
    ```
    git checkout <commit-ish> -- <file_path>
    ```
    
    ## List all the alias and configs.
    
    ```jsx
    git config --list
    ```
    
    ## Skip staging area during commit.
    
    ```jsx
    git commit --only <file_path>
    ```
    
    ## List n last commits
    
    ```jsx
    git log -<n>
    ```
    
    ## Clone a single branch
    
    ```
    git clone -b <branch-name> --single-branch https://github.com/user/repo.git
    ```
    
    ## Turn off git colored terminal output
    
    ```jsx
    git config --global color.ui false
    ```
    
    ## Unstaging Staged file
    
    ```
    git reset HEAD <file-name>
    ```
    
    ## Number of commits in a branch
    
    ```jsx
    git rev-list --count <branch-name>
    ```
    
    ## Find common ancestor of two branches
    
    ```
    git merge-base <branch-name> <other-branch-name>
    ```
    
    ## List unpushed git commits
    
    ```
    git log --branches --not --remotes
    ```
    
    ## Backup untracked files.
    
    ```jsx
    git ls-files --others -i --exclude-standard | xargs zip untracked.zip
    ```
    
    ## Show git status short
    
    ```jsx
    git status --short --branch
    ```
    - Great Tips
    
    ## Do commit early and often
    
    Git only takes full responsibility for your data when you commit. If you fail to commit and then do something poorly thought out, you can run into trouble. Additionally, having periodic checkpoints means that you can understand how you broke something.
    
    - *Commit Early And Often*
    
    ## Do make useful commit messages
    
    Creating insightful and descriptive commit messages is one of the best things you can do for others who use the repository. It lets people quickly understand changes without having to read code. When doing history archeology to answer some question, good commit messages likewise become very important.
    
    - The normal git rule of using the first line to provide a short (50-72 character) summary of the change is also very good.
    
    ## Do backups
    
    Everyone always recommends taking backups as best practice, and I am going to do the same. However, you already may have a highly redundant distributed ad-hoc backup system in place! This is because essentially every clone is a backup. 
    
    - In many cases, you may want to use a clone for git experiments to perfect your method before trying it for real
    
    ## Don’t change published history
    
    Once you `git push` (or in theory someone pulls from your repo, but people who pull from a working repo often deserve what they get) your changes to the authoritative upstream repository or otherwise make the commits or tags publicly visible, you should ideally consider those commits etched in diamond for all eternity. If you later find out that you messed up, make new commits that fix the problems (possibly by revert, possibly by patching, etc).
    
    - Yes, of course git allows you to rewrite public history, but it is problematic for everyone and thus it is just not best practice to do so.
