- GitHub Actions
    - Advanteges
        - Fully integrated with GitHub
        - Respond to any GitHub event
        - Community-powered workflows
        - Any platform, any language, any cloud.
    - Key functionalities
        - use on Linux, mac and windows
        - matrix builds
        - Streaming, searchable, linkable logs
        - built=in secret store
        - easy to write and easy to share.
    - GitHub Actions
        - event
        - workflow
        - action
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/69743224-6cc2-475b-a51a-dac286021ecb/Untitled.png)
        
    - Events
        
        ### [Events](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#events)
        
        An event is a specific activity in a repository that triggers a workflow run. For example, activity can originate from GitHub when someone creates a pull request, opens an issue, or pushes a commit to a repository. You can also trigger a workflow to run on a schedule, by [posting to a REST API](https://docs.github.com/en/rest/repos#create-a-repository-dispatch-event), or manually.
        
    - Actions
        
        ### [Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#actions)
        
        An *action* is a custom application for the GitHub Actions platform that performs a complex but frequently repeated task. Use an action to help reduce the amount of repetitive code that you write in your workflow files. An action can pull your git repository from GitHub, set up the correct toolchain for your build environment, or set up the authentication to your cloud provider.
        
        - Reusable units of code
        - Referencing vs authoring ACtions
        - Administrative features
        - Storing shared Actions
        - Post your acitons to the GitHub Markeyplace
    - WorkFlows
        
        ### [Workflows](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#workflows)
        
        A workflow is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule.
        
    - Types of Actions
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cbbe55be-3ad7-4be7-b72c-42c3bdeb51bf/Untitled.png)
        
    - Jobs
        
        ### [Jobs](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#jobs)
        
        A job is a set of *steps* in a workflow that is executed on the same runner. Each step is either a shell script that will be executed, or an *action* that will be run. Steps are executed in order and are dependent on each other. Since each step is executed on the same runner, you can share data from one step to another.
        
    - Runners
        
        ### [Runners](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#runners)
        
        A runner is a server that runs your workflows when they're triggered. Each runner can run a single job at a time.
