# Learning-Git 👨‍💻

- 1. ****What is Version Control?****
    
    # General Idea:
    
    1. Create things
    2. Save things
    3. Edit things
    4. Save the thing Again
    
    # Where it does the heavy lifting
    
    1. Git is a fast and modern implementation of version control.
    2. Git provides a history of content changes.
    3. Git facilitates collaborative changes to files.
    4. Git is easy to use for any type of knowledge worker.
    
    # Summary:
    
    A great tool for saving  and keep track of your progress, striking critically when you are working as a team in a collaborative project and even editing the same file.
    
- 2. ****What is Git?****
    
    # Local Git
    
    - Distributed so that connectivity doesn’t block work
    - Easy so that learning it’s commands can happen progressively
    
    # Distributed Git
    
    - Team-centric so that collaboration happens naturally
    
    # Distributed Git
    
    - Flexible so that it first your need instead of the other way around
    - Powerful to satisfying the scripting needs of the advanced developers
        
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6931588c-4282-40b7-84a1-d0dd2d693511/Untitled.png)
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/16e51ed2-a43a-4f17-b0cb-029a40f88c7b/Untitled.png)
        
- 3. ****Get Going with Git****
    - Download Git.
    - Set configuration ( Name & Email ).
    - Creates my first Project:
    
    ```jsx
    cd prok
    git init
    git add .
    git commit -m "commit message"
    ```
    
- 4. ****Quick Wins with Git****
    - Content, not files.
    - Be Explicit, not general.
    - Open, not locked.
    - Distributed Collaboration.
    - Conversation is supported in the GitHub Website in Issues for example.
    - Focus on People, not tools.
    - Journal, not backup.
    - Anywhere, not just online.
---

# Getting Started with Git

## 1. Setting Up A Repository

- git init
    - bare repository
- git clone
    - The copied Repo is connected to the original repository
    - gtt close - -bare
    - git  clone - - mirror
    - **Shallow clone**
    
    ```jsx
    git clone -depth=1 <repo>
    ```
    
- git config
    
    ```jsx
    git config user.email // husamzinap@gmail.com
    git config user.name // Husam-AbuZina
    ```
    
    ## **git config levels and files**
    
    - Local
    - Global
    - System
    
    ## **git config editor - core.editor**
    
    Many Git commands will launch a text editor to prompt for further input. One of the most common use cases for `git config` is configuring which editor Git should use. Listed below is a table of popular editors and matching `git config` commands:
    
    | Editor | config command |
    | --- | --- |
    | Atom | ~ git config --global core.editor "atom --wait"~ |
    | emacs | ~ git config --global core.editor "emacs"~ |
    | nano | ~ git config --global core.editor "nano -w"~ |
    | vim | ~ git config --global core.editor "vim"~ |
    | Sublime Text (Mac) | ~ git config --global core.editor "subl -n -w"~ |
    | Sublime Text (Win, 32-bit install) | ~ git config --global core.editor "'c:/program files (x86)/sublime text 3/sublimetext.exe' -w"~ |
    | Sublime Text (Win, 64-bit install) | ~ git config --global core.editor "'c:/program files/sublime text 3/sublimetext.exe' -w"~ |
    | Textmate | ~ git config --global core.editor "mate -w"~ |
    
    ## **Colored outputs**
    
    # `color.ui`
    
    This is the master variable for Git colors. Setting it to false will disable all Git's colored terminal output.
    
    ```
    $ git config --global color.ui false
    $ git config --global color.ui true
    ```
    
    ## **Git color configuration settings**
    
    1. `color.branch`
    
    - Configures the output color of the Git branch command
    
    2. `color.branch.`<`slot`>
    
    - This value is also applicable to Git branch output. <`slot`> is one of the following:
        - 1. current: the current branch
        - 2. local: a local branch
        - 3. remote: a remote branch ref in refs/remotes
        - 4. upstream: an upstream tracking branch
        - 5. plain: any other ref
    
    3. `color.diff`
    
    - Applies colors to `git diff`, `git log`, and `git show` output
    
    4. `color.diff`.<`slot`>
    
    - Configuring a <`slot`> value under `color.diff` tells git which part of the patch to use a specific color on.
        - 1. context: The context text of the diff. Git context is the lines of text content shown in a diff or patch that highlights changes.
        - 2. plain: a synonym for context
        - 3. meta: applies color to the meta information of the diff
        - 4. frag: applies color to the "hunk header" or "function in hunk header"
        - 5. old: applies a color to the removed lines in the diff
        - 6. new: colors the added lines of the diff
        - 7. commit: colors commit headers within the diff
        - 8. whitespace: sets a color for any whitespace errors in a diff
    
    ## **Aliases**
    
    they're custom shortcuts that define which command will expand to longer or combined commands.
    
    ```css
    
    git config --global alias.ci commit
    ```
    
    This example creates a ci alias for the `git commit` command. You can then invoke `git commit` by executing `git ci`. Aliases can also reference other aliases to create powerful combos.
    
    ## **Formatting & whitespace**
    
    Git has several "whitespace" features that can be configured to highlight whitespace issues when using git diff. The whitespace issues will be highlighted using the configured color `color.diff.whitespace`
    
    The following features are enabled by default:
    
    - `blank-at-eol` highlights orphan whitespaces at the line endings
    - `space-before-tab` highlights a space character that appears before a tab character when indenting a line
    - `blank-at-eof` highlights blank lines inserted at the end of a file
    
    The following features are disabled by default
    
    - `indent-with-non-tab` highlights a line that is indented with spaces instead of tabs
    - `tab-in-indent` highlights an initial tab indent as an error
    - `trailing-space` is shorthand for both blank-at-eol and blank-at-eof
    - `cr-at-eol highlights` a carriage-return at the line endings
    - `tabwidth=` defines how many character positions a tab occupies. The default value is 8. Allowed values are 1-63
    
    ## **Summary**
    
    In this article, we covered the use of the git `config command`. We discussed how the command is a convince method for editing raw `git config` files on the filesystem. We looked at basic read and write operations for confi
    
    - How to configure the Git editor
    - How to override configuration levels
    - How to reset configuration defaults
    - How to customize git colors
    
    Overall, `git config` is a helper tool that provides a shortcut to editing raw `git config` files on disk. We covered in depth personal customization options. Basic knowledge of git configuration options is a prerequisite for [setting up a repository](https://www.atlassian.com/git/tutorials/setting-up-a-repository). See our guide there for a demonstration of the basics.
    
- git alias
    
    ## **Git Alias Overview**
    
    To better understand Git aliases let us create some examples.
    
    ```jsx
    $ git config --global alias.co checkout
    $ git config --global alias.br branch
    $ git config --global alias.ci commit
    $ git config --global alias.st status
    ```
    
    ## Example
    
    ```jsx
    git config --global alias.unstage 'reset HEAD --'
    ```
    
    The preceding code example creates a new alias unstage. This now enables the invocation of git unstage. git unstage which will perform a reset on the staging area. This makes the following two commands equivalent.
    
    ```jsx
    git unstage fileA
    $ git reset HEAD -- fileA
    ```
    
    # How do I create Git Aliases?
    
    Aliases can be created through two primary methods:
    
    ### **Directly editing Git config files**
    
    The global or local config files can be manually edited and saved to create aliases. The global config file lives at `$HOME/.gitconfig` file path. The local path lives within an active git repository at `/.git/config`
    
    The config files will respect an `[alias]` section that looks like:
    
    `[alias]
     co = checkout`
    
    This means that `co` is a shortcut for `checkout`
    
    ### **Using the git config to create aliases**
    

---

## 2. Saving Changes

- git add
    - the stash
        
        Git has an additional saving mechanism called 'the stash'. The stash is an ephemeral storage area for changes that are not ready to be committed. The stash operates on the working directory, the first of [the three trees](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset) and has extensive usage options. To learn more visit the `git stash` page.
        
        - Difference between git add and git stash
            1. **Staging Area (Index)**:
            The staging area is an intermediate step in the Git workflow that acts as a buffer between your working directory and the repository's commit history. When you make changes to files in your working directory, you need to explicitly add those changes to the staging area before they become part of a commit. In other words, the staging area is where you prepare and organize the changes you want to include in the next commit.
            
            1. **Stash**:
            The stash, on the other hand, is a mechanism for saving and temporarily setting aside uncommitted changes in your working directory and the staging area. It allows you to save work in progress without committing it. When you run **`git stash`**, Git takes all the changes in your working directory and the staging area and saves them in a temporary storage area (the stash). This reverts your working directory and staging area back to the state of the last commit, effectively giving you a clean slate.
                
                Later, when you need to retrieve your stashed changes, you can use **`git stash apply`** or **`git stash pop`** to reapply the saved changes back to your working directory and staging area. The stash itself remains intact even after applying or popping the changes, allowing you to reuse or apply the stash to different branches if needed.
                
        
    - .git ignore
        
        A Git repository can be configured to ignore specific files or directories. This will prevent Git from saving changes to any ignored content. Git has multiple methods of configuration that manage the ignore list. Git ignore configure is discussed in further detail on the `git ignore` page.
        
    - git add
        - It tells Git that you want to include updates to a particular file in the next commit. However, `git add` doesn't really affect the repository in any significant way—changes.
        - The `git add` command should not be confused with `svn add`, which adds a file to the repository. Instead, `git add` works on the more abstract level of changes. This means that `git add` needs to be called every time you alter a file, whereas `svn add` only needs to be called once for each file. It may sound redundant, but this workflow makes it much easier to keep a project organized.
        - The primary function of the `git add` command, is to promote pending changes in the working directory, to the `git staging` area. The staging area is one of Git's more unique features, and it can take some time to wrap your head around it if you’re coming from an SVN (or even a Mercurial) background. It helps to think of it as a buffer between the working directory and the project history. The staging area is considered one of the ["three trees" of Git](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset), along with, the working directory, and the commit history.
    - git status
        
        `git status` to view the state of the working directory and the staging area.
        
    - git push
        
        `git push` is utilized to send the committed changes to remote repositories for collaboration. This enables other team members to access a set of saved changes.
        
    - Common Options
        
        # Common options
        
        `git add <file>`
        
        Stage all changes in `<file>` for the next commit.
        
        `git add <directory>`
        
        Stage all changes in `<directory>` for the next commit.
        
        `git add -p`
        
        Begin an interactive staging session that lets you choose portions of a file to add to the next commit. This will present you with a chunk of changes and prompt you for a command. Use `y` to stage the chunk, `n` to ignore the chunk, `s` to split it into smaller chunks, `e` to manually edit the chunk, and `q` to exit.
        
- git commit
    - Notes
        - A commit is the Git equivalent of a "save”
        - These two commands `git commit` and `git add` are two of the most frequently used.
        - In Git, repositories are distributed, Snapshots are committed to the local repository, and this requires absolutely no interaction with other Git repositories. Git commits can later be pushed to arbitrary remote repositories.
        - Comments in Bash:
        
        ```jsx
        # This is a single-line comment in Bash
        echo "Hello, World!" # This part of the line is also a comment
        ```
        
    - Snapshots, not differences
        - For example, a SVN commit consists of a diff compared to the original file added to the repository. Git, on the other hand, records the entire contents of each file in every commit.
        - This makes many Git operations much faster than SVN, since a particular version of a file doesn’t have to be “assembled” from its diffs—the complete revision of each file is immediately available from Git's internal database.
    - Common options
        
        `git commit`
        
        Commit the staged snapshot. This will launch a text editor prompting you for a commit message. After you’ve entered a message, save the file and close the editor to create the actual commit.
        
        `git commit -a`
        
        Commit a snapshot of all changes in the working directory. 
        
        `git commit -m "commit message"`
        
        A shortcut command that immediately creates a commit with a passed commit message. By default, `git commit` will open up the locally configured text editor, and prompt for a commit message to be entered.
        
        `git commit -am "commit message"`
        
        A power user shortcut command that combines the `-a` and `-m` options. This combination immediately creates a commit of all the staged changes and takes an inline commit message.
        
        `git commit --amend`
        
        This option adds another level of functionality to the commit command.  This command will open up the system's configured text editor and prompt to change the previously specified commit message.
        
        # How to update (amend) a commit
        
        To continue with the `hello.py` example above. Let's make further updates to `hello.py` and execute the following:
        
        `git add hello.py
        git commit --amend`
        
        This will once again, open up the configured text editor. This time, however, it will be pre-filled with the commit message we previously entered. This indicates that we are not creating a new commit, but editing the last.
        
        # The **`--amend`** option is handy when you want to:
        
        1. **Add forgotten changes:** If you realize that you forgot to include some changes in the last commit, you can stage the forgotten changes and then use **`git commit --amend`** to add them to the previous commit.
        2. **Edit the commit message:** By using **`git commit --amend`**, you can modify the commit message of the most recent commit.
        3. **Combine small commits:** If you have made several small commits that you wish to group together or merge into a single commit, you can use **`git commit --amend`** to combine the changes of the last commit with your new changes and update the commit message accordingly.
        
    - Commit message
        
        Git doesn't require commit messages to follow any specific formatting constraints, but the canonical format is to summarize the entire commit on the first line in less than 50 characters, leave a blank line, then a detailed explanation of what’s been changed. 
        
        ## For example:
        
        ```jsx
        # Change the message displayed by hello.py
        
        - Update the sayHello() function to output the user's name
        - Change the sayGoodbye() function to a friendlier message
        ```
        
        It is a common practice to use the first line of the commit message as a subject line, similar to an email. The rest of the log message is considered the body and used to communicate details of the commit change set. Note that many developers also like to use the present tense in their commit messages. This makes them read more like actions on the repository, which makes many of the history-rewriting operations more intuitive.
        
- git diff
    - Notes
        - 
    - Reading diffs: outputs
        
        # Raw output format
        
        The following examples will be executed in a simple repo. The repo is created with the commands below:
        
        `$:> mkdir diff_test_repo
        $:> cd diff_test_repo
        $:> touch diff_test.txt
        $:> echo "this is a git diff test example" > diff_test.txt
        $:> git init .
        Initialized empty Git repository in /Users/kev/code/test/.git/
        $:> git add diff_test.txt
        $:> git commit -am"add diff test file"
        [main (root-commit) 6f77fc3] add diff test file
        1 file changed, 1 insertion(+)
        create mode 100644 diff_test.txt`
        
        If we execute `git diff` at this point, there will be no output. This is expected behavior as there are no changes in the repo to diff. Once the repo is created and we've added the `diff_test.txt` file, we can change the contents of the file to start experimenting with diff output.
        
        `$:> echo "this is a diff example" > diff_test.txt`
        
        Executing this command will change the content of the `diff_test.txt` file. Once modified, we can view a diff and analyze the output. Now executing `git diff` will produce the following output:
        
        `diff --git a/diff_test.txt b/diff_test.txt
        index 6b0c6cf..b37e70a 100644
        --- a/diff_test.txt
        +++ b/diff_test.txt
        @@ -1 +1 @@
        -this is a git diff test example
        +this is a diff example`
        
        Let us now examine a more detailed breakdown of the diff output.
        
        # 1. Comparison input
        
        `diff --git a/diff_test.txt b/diff_test.txt`
        
        This line displays the input sources of the diff. We can see that `a/diff_test.txt` and `b/diff_test.txt` have been passed to the diff.
        
        # 2. Meta data
        
        `index 6b0c6cf..b37e70a 100644`
        
        This line displays some internal Git metadata. You will most likely not need this information. The numbers in this output correspond to Git object version hash identifiers.
        
        # 3. Markers for changes
        
        - `-- a/diff_test.txt
        +++ b/diff_test.txt`
        
        These lines are a legend that assigns symbols to each diff input source. In this case, changes from `a/diff_test.txt` are marked with a `---` and the changes from `b/diff_test.txt` are marked with the `+++` symbol.
        
        # 4. Diff chunks
        
        The remaining diff output is a list of diff 'chunks'. A diff only displays the sections of the file that have changes. In our current example, we only have one chunk as we are working with a simple scenario. Chunks have their own granular output semantics.
        
        `@@ -1 +1 @@
        -this is a git diff test example
        +this is a diff example`
        
        The first line is the chunk header. Each chunk is prepended by a header enclosed within `@@` symbols. The content of the header is a summary of changes made to the file. In our simplified example, we have -1 +1 meaning line one had changes. In a more realistic diff, you would see a header like:
        
        `@@ -34,6 +34,8 @@`
        
        In this header example, 6 lines have been extracted starting from line number 34. Additionally, 8 lines have been added starting at line number 34.
        
        The remaining content of the diff chunk displays the recent changes. Each changed line is prepended with a `+` or `-` symbol indicating which version of the diff input the changes come from. As we previously discussed, `-` indicates changes from the `a/diff_test.txt` and + indicates changes from `b/diff_test.txt`.
        
    - HighLight Changes
        
        # Highlighting changes
        
        # 1. `git diff --color-words`
        
        `git diff` also has a special mode for highlighting changes with much better granularity: `‐‐color-words`. This mode tokenizes added and removed lines by whitespace and then diffs those.
        
        `$:> git diff --color-words
        diff --git a/diff_test.txt b/diff_test.txt
        index 6b0c6cf..b37e70a 100644
        --- a/diff_test.txt
        +++ b/diff_test.txt
        @@ -1 +1 @@
        this is agit difftest example`
        
        Now the output displays only the color-coded words that have changed.
        
        # 2. `git diff-highlight`
        
        If you clone the git source, you’ll find a sub-directory called contrib. It contains a bunch of git-related tools and other interesting bits and pieces that haven’t yet been promoted to git core. One of these is a Perl script called diff-highlight. Diff-highlight pairs up matching lines of diff output and highlights sub-word fragments that have changed.
        
        `$:> git diff | /your/local/path/to/git-core/contrib/diff-highlight/diff-highlight
        diff --git a/diff_test.txt b/diff_test.txt
        index 6b0c6cf..b37e70a 100644
        --- a/diff_test.txt
        +++ b/diff_test.txt
        @@ -1 +1 @@
        -this is a git diff test example
        +this is a diff example`
        
        Now we’ve pared down our diff to the smallest possible change.
        
    - **Diffing binary files**
        
        # Diffing binary files
        
        In addition to the text file utilities we have thus far demonstrated, `git diff` can be run on binary files. Unfortunately, the default output is not very helpful.
        
        `$:> git diff
        Binary files a/script.pdf and b/script.pdf differ`
        
        Git does have a feature that allows you to specify a shell command to transform the content of your binary files into text prior to performing the diff. It does require a little set up though. First, you need to specify a textconv filter describing how to convert a certain type of binary to text. We're using a simple utility called pdftohtml (available via homebrew) to convert my PDFs into human readable HTML. You can set this up for a single repository by editing your `.git/config` file, or globally by editing `~ /.gitconfig`
        
        `[diff "pdfconv"]
        textconv=pdftohtml -stdout`
        
        Then all you need to do is associate one or more file patterns with our pdfconv filter. You can do this by creating a `.gitattributes` file in the root of your repository.
        
        - `.pdf diff=pdfconv`
        
        Once configured, `git diff` will first run the binary file through the configured converter script and diff the converter output. The same technique can be applied to get useful diffs from all sorts of binary files, for example: zips, jars and other archives: using `unzip -l` (or similar) in place of pdf2html will show you paths that have been added or removed between commits images: exiv2 can be used to show metadata changes such as image dimensions documents: conversion tools exist for transforming .odf, .doc and other document formats to plain text. In a pinch, strings will often work for binary files where no formal converter exists.
        
    - **Comparing files: git diff file**
        
        # Comparing files: git diff file
        
        The `git diff` command can be passed an explicit file path option. When a file path is passed to `git diff` the diff operation will be scoped to the specified file. The below examples demonstrate this usage.
        
        `git diff HEAD ./path/to/file`
        
        This example is scoped to `./path/to/file` when invoked, it will compare the specific changes in the working directory, against the index, showing the changes that are not staged yet. By default `git diff` will execute the comparison against `HEAD`. Omitting `HEAD` in the example above `git diff ./path/to/file` has the same effect.
        
        `git diff --cached ./path/to/file`
        
        When `git diff` is invoked with the `--cached` option the diff will compare the staged changes with the local repository. The `--cached` option is synonymous with `--staged`.
        
    - **Changes since last commit**
        
        By default `git diff` will show you any uncommitted changes since the last commit.
        
        ```jsx
        git diff
        ```
        
    - **Comparing files between two different commits**
        
        `git diff` can be passed Git refs to commits to diff. Some example refs are, `HEAD`, tags, and branch names. Every commit in Git has a commit ID which you can get when you execute `GIT LOG`. You can also pass this commit ID to `git diff`.
        
        ```jsx
        git log --pretty=oneline
        957fbc92b123030c389bf8b4b874522bdf2db72c add feature
        ce489262a1ee34340440e55a0b99ea6918e19e7a rename some classes
        6b539f280d8b0ec4874671bae9c6bed80b788006 refactor some code for feature
        646e7863348a427e1ed9163a9a96fa759112f102 add some copy to body
        
        $:> git diff 957fbc92b123030c389bf8b4b874522bdf2db72c ce489262a1ee34340440e55a0b99ea6918e19e7a
        ```
        
    - **Comparing branches**
        
        # Comparing two branches
        
        Branches are compared like all other ref inputs to `git diff`
        
        `git diff branch1..other-feature-branch`
        
        This example introduces the dot operator. The two dots in this example indicate the diff input is the tips of both branches. The same effect happens if the dots are omitted and a space is used between the branches. Additionally, there is a three dot operator:
        
        `git diff branch1...other-feature-branch`
        
        The three dot operator initiates the diff by changing the first input parameter `branch1`. It changes `branch1` into a ref of the shared common ancestor commit between the two diff inputs, the shared ancestor of `branch1` and other-feature-branch. The last parameter input parameter remains unchanged as the tip of other-feature-branch.
        
    - **Comparing files from two branches**
        
        To compare a specific file across branches, pass in the path of the file as the third argument to `git diff`
        
        ```jsx
        git diff main new_branch ./diff_test.txt
        ```
        
    - Summary
        
        # Summary
        
        This page disscused the Git diffing process and the `git diff` command. We discussed how to read `git diff` output and the various data included in the output. Examples were provided on how to alter the `git diff` output with highlighting and colors. We discussed different diffing strategies such as how to diff files in branches and specific commits. In addition to the `git diff` command, we also used `git log` and `git checkout`.
        
- git stash
    
    
    <aside>
    💡 Note that the stash is local to your Git repository; stashes are not transferred to the server when you push.
    
    </aside>
    
    - Example of Stash
        
        # For Example:
        
        ```jsx
        $ git status
        On branch main
        Changes to be committed:
        
            new file:   style.css
        
        Changes not staged for commit:
        
            modified:   index.html
        
        $ git stash
        Saved working directory and index state WIP on main: 5002d47 our new homepage
        HEAD is now at 5002d47 our new homepage
        
        $ git status
        On branch main
        nothing to commit, working tree clean
        ```
        
    - **Re-applying your stashed changes**
        
        You can reapply previously stashed changes with `git stash pop`:
        
        ```jsx
        $ git status
        On branch main
        nothing to commit, working tree clean
        $ git stash pop
        On branch main
        Changes to be committed:
        
            new file:   style.css
        
        Changes not staged for commit:
        
            modified:   index.html
        
        Dropped refs/stash@{0} (32b3aa1d185dfe6d57b3c3cc3b32cbf3e380cc6a)
        ```
        
        Alternatively, you can  re use the  stach with `git stash apply`:
        
    - **Stashing untracked or ignored files**
        
        
        # `git stash`  Will:
        
        ## stash:
        
        - changes that have been added to your index (staged changes)
        - changes made to files that are currently tracked by Git (unstaged changes)
        
        ## **not** stash:
        
        - new files in your working copy that have not yet been staged
        - files that have been [ignored](https://www.atlassian.com/git/tutorials/saving-changes/gitignore)
        
        <aside>
        💡 Adding the `-u` option (or `--include-untracked`) tells `git stash` to also stash your untracked files:
        
        </aside>
        
        <aside>
        💡 You can include changes to [ignored](https://www.atlassian.com/git/tutorials/gitignore) files as well by passing the `-a` option (or `--all`) when running `git stash`.
        
        </aside>
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/42180157-d7f7-4f99-a476-862f4a22a755/Untitled.png)
        
    - **Managing multiple stashes**
        
        You aren't limited to a single stash. You can run `git stash` several times to create multiple stashes, and then use `git stash list` to view them. By default, stashes are identified simply as a "WIP" – work in progress – on top of the branch and commit that you created the stash from. After a while it can be difficult to remember what each stash contains:
        
        ```jsx
        $ git stash list
        stash@{0}: WIP on main: 5002d47 our new homepage
        stash@{1}: WIP on main: 5002d47 our new homepage
        stash@{2}: WIP on main: 5002d47 our new homepage
        ```
        
        To provide a bit more context, it's good practice to annotate your stashes with a description, using `git stash save "message"`:
        
        ```jsx
        $ git stash save "add style to our site"
        Saved working directory and index state On main: add style to our site
        HEAD is now at 5002d47 our new homepage
        ``
        ```
        
        By default, `git stash pop` will re-apply the most recently created stash: `stash@{0}`
        
        You can choose which stash to re-apply by passing its identifier as the last argument, for example:
        
        ```jsx
        $ git stash pop stash@{2}
        ```
        
        By default, `git stash pop` will re-apply the most recently created stash: `stash@{0}`
        
        You can choose which stash to re-apply by passing its identifier as the last argument, for example:
        
        ```jsx
        $ git stash pop stash@{2}
        ```
        
    - **Viewing stash diffs**
        
        You can view a summary of a stash with `git stash show`:
        
        ```jsx
        $ git stash show
         index.html | 1 +
         style.css | 3 +++
         2 files changed, 4 insertions(+)
        ```
        
        Or pass the `-p` option (or `--patch`) to view the full diff of a stash:
        
        ```jsx
        $ git stash show -p
        diff --git a/style.css b/style.css
        new file mode 100644
        index 0000000..d92368b
        --- /dev/null
        +++ b/style.css
        @@ -0,0 +1,3 @@
        +* {
        +  text-decoration: blink;
        +}
        diff --git a/index.html b/index.html
        index 9daeafb..ebdcbd2 100644
        --- a/index.html
        +++ b/index.html
        @@ -1 +1,2 @@
        +<link rel="stylesheet" href="style.css"/>
        ```
        
    - **Partial stashes**
        
        You can also choose to stash just a single file, a collection of files, or individual changes from within files. If you pass the `-p` option (or `--patch`) to `git stash`, it will iterate through each changed "hunk" in your working copy and ask whether you wish to stash it:
        
        | Command | Description |
        | --- | --- |
        | / | search for a hunk by regex |
        | ? | help |
        | n | don't stash this hunk |
        | q | quit (any hunks that have already been selected will be stashed) |
        | s | split this hunk into smaller hunks |
        | y | stash this hunk |
        
        `CTRL-C`
        
    - **Creating a branch from your stash**
        
        If the changes on your branch diverge from the changes in your stash, you may run into conflicts when popping or applying your stash. Instead, you can use `git stash branch` to create a new branch to apply your stashed changes to:
        
    - **Cleaning up your stash**
        
        If you decide you no longer need a particular stash, you can delete it with `git stash drop`:
        
        ```jsx
        $ git stash drop stash@{1}
        Dropped stash@{1} (17e2697fd8251df6163117cb3d58c1f62a5e7cdb)
        ```
        
        Or you can delete all of your stashes with:
        
        ```jsx
        $ git stash clear
        ```
        
    - **How git stash works**
        
        Stashes are actually encoded in your repository as commit objects. The special ref at `.git/refs/stash` points to your most recently created stash, and previously created stashes are referenced by the `stash` ref's reflog. This is why you refer to stashes by `stash@{n}:` you're actually referring to the nth reflog entry for the `stash` ref. Since a stash is just a commit, you can inspect it with `git log`:
        
        ```jsx
        $ git log --oneline --graph stash@{0}
        *-.   953ddde WIP on main: 5002d47 our new homepage
        |\ \ 
        | | * 24b35a1 untracked files on main: 5002d47 our new homepage
        | * 7023dd4 index on main: 5002d47 our new homepage
        |/ 
        * 5002d47 our new homepage
        ```
        
        How `git stash` encodes your worktree and index as commits:
        
        - Before stashing, your worktree may contain changes to tracked files, untracked files, and ignored files. Some of these changes may also be staged in the index.
            
            !https://wac-cdn.atlassian.com/dam/jcr:3a2ede93-1f2d-45ae-9e0b-167cc0362f37/03.svg?cdnVersion=1134
            
        - Invoking `git stash` encodes any changes to tracked files as two new commits in your DAG: one for unstaged changes, and one for changes staged in the index. The special `refs/stash` ref is updated to point to them.
            
            !https://wac-cdn.atlassian.com/dam/jcr:35edaf68-e8b1-484e-b5f0-292c532f048a/04.svg?cdnVersion=1134
            
        - Using the `-include-untracked` option also encodes any changes to untracked files as an additional commit.
            
            !https://wac-cdn.atlassian.com/dam/jcr:f7dd5493-a98d-449e-ae37-146d6270ccf7/05.svg?cdnVersion=1134
            
        - Using the `-all` option includes changes to any ignored files alongside changes to untracked files in the same commit.
            
            !https://wac-cdn.atlassian.com/dam/jcr:446fad60-0ff5-4383-8177-a5fc2813364d/06.svg?cdnVersion=1134
            
            <aside>
            💡 When you run `git stash pop`, the changes from the commits above are used to update your working copy and index, and the stash reflog is shuffled to remove the popped commit. Note that the popped commits aren't immediately deleted, but do become candidates for future garbage collection.
            
            </aside>
            
    
- .gitignore
    - Intro
        
        Git sees every file in your working copy as one of three things:
        
        1. tracked - a file which has been previously staged or committed;
        2. untracked - a file which *has not* been staged or committed; or
        3. ignored - a file which Git has been explicitly told to ignore.
            
            Ignored files are usually build artifacts and machine generated files that can be derived from your repository source or should otherwise not be committed. 
            
            # Some common examples are:
            
            - dependency caches, such as the contents of `/node_modules` or `/packages`
            - compiled code, such as `.o`, `.pyc`, and `.class` files
            - build output directories, such as `/bin`, `/out`, or `/target`
            - files generated at runtime, such as `.log`, `.lock`, or `.tmp`
            - hidden system files, such as `.DS_Store` or `Thumbs.db`
            - personal IDE config files, such as `.idea/workspace.xml`
    - Use Cases Table
        
        `.gitignore` uses [globbing patterns](http://linux.die.net/man/7/glob) to match against file names. You can construct your patterns using various symbols:
        
        | Pattern | Example matches | Explanation* |
        | --- | --- | --- |
        | **/logs | logs/debug.loglogs/monday/foo.barbuild/logs/debug.log | You can prepend a pattern with a double asterisk to match directories anywhere in the repository. |
        | **/logs/debug.log | logs/debug.logbuild/logs/debug.logbut notlogs/build/debug.log | You can also use a double asterisk to match files based on their name and the name of their parent directory. |
        | *.log | debug.logfoo.log.loglogs/debug.log | An asterisk is a wildcard that matches zero or more characters. |
        | *.log!important.log | debug.logtrace.logbut notimportant.loglogs/important.log | Prepending an exclamation mark to a pattern negates it. If a file matches a pattern, but also matches a negating pattern defined later in the file, it will not be ignored. |
        | *.log!important/*.logtrace.* | debug.logimportant/trace.logbut notimportant/debug.log | Patterns defined after a negating pattern will re-ignore any previously negated files. |
        | /debug.log | debug.logbut notlogs/debug.log | Prepending a slash matches files only in the repository root. |
        | debug.log | debug.loglogs/debug.log | By default, patterns match files in any directory |
        | debug?.log | debug0.logdebugg.logbut notdebug10.log | A question mark matches exactly one character. |
        | debug[0-9].log | debug0.logdebug1.logbut notdebug10.log | Square brackets can also be used to match a single character from a specified range. |
        | debug[01].log | debug0.logdebug1.logbut notdebug2.logdebug01.log | Square brackets match a single character form the specified set. |
        | debug[!01].log | debug2.logbut notdebug0.logdebug1.logdebug01.log | An exclamation mark can be used to match any character except one from the specified set. |
        | debug[a-z].log | debuga.logdebugb.logbut notdebug1.log | Ranges can be numeric or alphabetic. |
        | logs | logslogs/debug.loglogs/latest/foo.barbuild/logsbuild/logs/debug.log | If you don't append a slash, the pattern will match both files and the contents of directories with that name. In the example matches on the left, both directories and files named logs are ignored |
        | logs/ | logs/debug.loglogs/latest/foo.barbuild/logs/foo.barbuild/logs/latest/debug.log | Appending a slash indicates the pattern is a directory. The entire contents of any directory in the repository matching that name – including all of its files and subdirectories – will be ignored |
        | logs/!logs/important.log | logs/debug.loglogs/important.log | Wait a minute! Shouldn't logs/important.log be negated in the example on the leftNope! Due to a performance-related quirk in Git, you can not negate a file that is ignored due to a pattern matching a directory |
        | logs/**/debug.log | logs/debug.loglogs/monday/debug.loglogs/monday/pm/debug.log | A double asterisk matches zero or more directories. |
        | logs/*day/debug.log | logs/monday/debug.loglogs/tuesday/debug.logbut notlogs/latest/debug.log | Wildcards can be used in directory names as well. |
        | logs/debug.log | logs/debug.logbut notdebug.logbuild/logs/debug.log | Patterns specifying a file in a particular directory are relative to the repository root. (You can prepend a slash if you like, but it doesn't do anything special.) |
        - * these explanations assume your .gitignore file is in the top level directory of your repository, as is the convention. If your repository has multiple .gitignore files, simply mentally replace "repository root" with "directory containing the .gitignore file" (and consider unifying them, for the sanity of your team).*
    - Add Comments
        
        In addition to these characters, you can use # to include comments in your `.gitignore` file:
        
        ```jsx
        # ignore all logs
        *.log
        ```
        
        You can use \ to escape `.gitignore` pattern characters if you have files or directories containing them:
        
        ```jsx
        # ignore the file literally named foo[01].txt
        foo\[01\].txt
        ```
        
    - **Shared .gitignore files in your repository**
        
        Git ignore rules are usually defined in a `.gitignore` file at the root of your repository. However, you can choose to define multiple `.gitignore` files in different directories in your repository. Each pattern in a particular `.gitignore` file is tested relative to the directory containing that file. However the convention, and simplest approach, is to define a single `.gitignore` file in the root. As your `.gitignore` file is checked in, it is versioned like any other file in your repository and shared with your teammates when you push. Typically you should only include patterns in `.gitignore` that will benefit other users of the repository.
        
    - **Personal Git ignore rules ( Stored Locally )**
        
        You can also define personal ignore patterns for a particular repository in a special file at `.git/info/exclude`. These are not versioned, and not distributed with your repository, so it's an appropriate place to include patterns that will likely only benefit you. For example if you have a custom logging setup, or special development tools that produce files in your repository's working directory, you could consider adding them to `.git/info/exclude` to prevent them from being accidentally committed to your repository.
        
    - **Global Git ignore rules**
        
        In addition, you can define global Git ignore patterns for all repositories on your local system by setting the Git `core.excludesFile` property. You'll have to create this file yourself. If you're unsure where to put your global `.gitignore` file, your home directory isn't a bad choice (and makes it easy to find later). Once you've created the file, you'll need to configure its location with `git config`:
        
        ```jsx
        $ touch ~/.gitignore
        $ git config --global core.excludesFile ~/.gitignore
        ```
        
        You should be careful what patterns you choose to globally ignore, as different file types are relevant for different projects. Special operating system files (e.g. `.DS_Store` and `thumbs.db`) or temporary files created by some developer tools are typical candidates for ignoring globally.
        
    - **Ignoring a previously committed file**
        
        If you want to ignore a file that you've committed in the past, you'll need to delete the file from your repository and then add a `.gitignore` rule for it. Using the `--cached` option with `git rm` means that the file will be deleted from your repository, but will remain in your working directory as an ignored file.
        
        ```jsx
        $ echo debug.log >> .gitignore
          
        $ git rm --cached debug.log
        rm 'debug.log'
          
        $ git commit -m "Start ignoring debug.log"
        ```
        
        You can omit the `--cached` option if you want to delete the file from both the repository and your local file system.
        
    - **Committing an ignored file**
        
        ed file to be committed to the repository using the `-f` (or `--force`) option with `git add`:
        
        ```jsx
        $ cat .gitignore
        *.log
          
        $ git add -f debug.log
          
        $ git commit -m "Force adding debug.log"
        ```
        
        You might consider doing this if you have a general pattern (like `*.log`) defined, but you want to commit a specific file. However a better solution is to define an exception to the general rule:
        
        ```jsx
        $ echo !debug.log >> .gitignore
          
        $ cat .gitignore
        *.log
        !debug.log
          
        $ git add debug.log
          
        $ git commit -m "Adding debug.log"
        ```
        
        This approach is more obvious, and less confusing, for your teammates.
        
    - **Stashing an ignored file**
        
        `git stash` is a powerful Git feature for temporarily shelving and reverting local changes, allowing you to re-apply them later on. As you'd expect, by default `git stash` ignores ignored files and only stashes changes to files that are tracked by Git. However, you can invoke [git stash with the --all option](https://www.atlassian.com/git/tutorials/saving-changes/git-stash#stashing-untracked-or-ignored) to stash changes to ignored and untracked files as well.
        
    - **Debugging .gitignore files**
        
        If you have complicated `.gitignore` patterns, or patterns spread over multiple `.gitignore` files, it can be difficult to track down why a particular file is being ignored. You can use the `git check-ignore` command with the `-v` (or `--verbose`) option to determine which pattern is causing a particular file to be ignored:
        
        ```jsx
        $ git check-ignore -v debug.log
        .gitignore:3:*.log  debug.lo
        ```
        
        The output shows:
        
        ```jsx
        <file containing the pattern> : <line number of the pattern> : <pattern>    <file name>
        ```
        
        You can pass multiple file names to `git check-ignore` if you like, and the names themselves don't even have to correspond to files that exist in your repository.      
