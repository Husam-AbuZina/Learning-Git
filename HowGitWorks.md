## How git works

- git tree
    
    ```jsx
    $ tree .git
    .git
    ├── HEAD
    ├── config
    ├── hooks
    ├── objects
    │ ├── info
    │ └── pack
    └── refs
     ├── heads
     └── tags
    ```
    
- Details of id
    - The hash is the id of the content in the git database.
    - The object id is computed solely based on the content. ( and is agnostic of the file name. )
    - If we were to have another file with a different name but with the same contents, the hash would be the same.
- Saving git blobs
    
    ## **Saving Git Blob object to Database**
    
    To write the file content to the git database, a -w flag may be added to the *hash-object* command.
    
    ```
    $ echo 'hello' | git hash-object --stdin -w
    ce013625030ba8dba906f756967f9e9ca394464a
    ```
    
    This will store the contents under a file in the **objects** directory with the object-id as the name
    
    ```
    $ tree .git
    .git
    ├── HEAD
    ├── config
    ├── hooks
    ├──objects
    │   ├──ce
    │   │   └──013625030ba8dba906f756967f9e9ca394464a
    │   ├── info
    │   └── pack
    └── refs
        ├── heads
        └── tags
    ```
    
- Making a commit
    
    ## **Making A Git Commit**
    
    Most will be familiar with the *git commit* command that makes a commit out of the changes in the staging area and updates the reference of the branch to that commit. Lets use the low level API to do the same.
    
    A commit object in git has a tree, a link to the parent commit if present and information such as the commit message and the details about the author and the committer.
    
    Lets start with the *dca98923d43cd634f4359f8a1f897bf585100cfe* *tree* which we have created in the last section.
    
    ```
    $ git commit-tree dca98923d43cd634f4359f8a1f897bf585100cfe -m "Commit Message" # Creates a commit with the changes in the tree and the messages
    1185a9903f20ca3059dcc96662fb05cc219bd654
    ```
    
    !https://miro.medium.com/v2/resize:fit:875/1*_yoc7P_cq7nilWNbpshJjw.png
    
    Commit has a message and points to a tree
    
    A commit with commit-id *1185a9903f20ca3059dcc96662fb05cc219bd654* has been created. You may see the commit with the command
    
    ```
    $git log 1185a9903f20ca3059dcc96662fb05cc219bd654
    commit 1185a9903f20ca3059dcc96662fb05cc219bd654
    Author: Praveen Mathew <email@email.com>
    Date:   Wed Feb 17 19:18:40 2021 +0530Commit Message
    ```
    
    Lets create another commit on top of it using the low level git APIs:
    
    ```
    $touch file2.txt$ git add file2.txt$ git write-tree
    5d649a7d0557d17655fbdd362b34158a36b0a39d$ git commit-tree 5d649a7d0557d17655fbdd362b34158a36b0a39d -m "Second Commit Message" -p 1185a9903f20ca3059dcc96662fb05cc219bd654 #
    7a4834354b351022ea9ddb818b7b2a889bdbb3cf
    
    ```
    
    !https://miro.medium.com/v2/resize:fit:875/1*j28cI9K_NEQNz_eAx862Dw.png
    
    commits also points to the parent commit
    
    Now the log of the commit *7a4834354b351022ea9ddb818b7b2a889bdbb3cf* would show both the commits
    
    ```
    $git log 7a4834354b351022ea9ddb818b7b2a889bdbb3cf --oneline
    7a48343 Second Commit Message
    1185a99 Commit Message
    ```
    
    However if you notice current branch pointed to by the HEAD is still the default one. The commits dont show up there.
    
    ```
    $git log
    fatal: your current branch 'main' does not have any commits yet
    ```
    
    Apart from creating the commits, there is one more thing that the git commit command does. It also updates the reference of the branch pointed to by the HEAD. That is done by the command *git update-ref*
    
    ```
    $ git update-ref refs/heads/main 7a4834354b351022ea9ddb818b7b2a889bdbb3cf # points main reference to the commit
    ```
    
    !https://miro.medium.com/v2/resize:fit:875/1*ppXGtt6A_BNz7094joGX2g.png
    
    reference has been updated to point to the latest commit
    
- [YouTube Video](https://www.youtube.com/watch?v=P6jD966jzlk&ab_channel=GitLab)
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9405101b-edff-41c9-95b8-fbb9c211b98a/Untitled.png)
    
    # What is SHA ?
    
    - Git takes a 40 character string made up depending on the contents of the project content.
    - Git Actually  order objects depending on the first two characters of the SHA.
    - 2 \ 39  ( the first two are a subdirectory )
    - git cat-file -p <SHA>
    - cat .git/index
    
- Git Objects - [YouTube Link](https://www.youtube.com/watch?v=MyvyqdQ3OjI&ab_channel=Brief)
    - Blob
        - Objects called Blobs store and contain the content of the files. ( binary objects )
        - Files contains a metadata. ( remembers when it was created )
        - Blobs does not remember anything but it’s content
        - Every blob is identified by a unique SHA
    - Tree
        - A Directory listing. ( referring to blobs and other trees )
        - Trees are identified by their unique SHA as well.
        - In another tree, same blob can have another name.
    - Commit
        - A snapshot of the working tree
        - Includes a pointer to the main tree ( root directory)
        - Include metadata ( created time, author, message, their parent commit )
        - has it’s own SHA. (   The same SHA we see when displaying git logs)f
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f0040928-b74f-4273-a6a5-9e599fd6ff17/Untitled.png)
        
    - What git stores at every commit
        
        ## The trick is:
        
        - Whenever an object does not change after the commit, we does not store it again until it get changed again.
        - Since it’s a second commit, it has a parent commit.
        - Instead of re storing the unchanged blobs objects, we just reference the old value hashes.
    - Notes
        - if we created a two blobs on different systems  with the same object, they will have the same hash SHA.
        - if we created a tree referencing each blob, also the two trees will have the same hash SHA.
        - BUT, if we made a commit on each tree on each system, they will have a different SHA because meta data will differ like: date, time, computer type, …
