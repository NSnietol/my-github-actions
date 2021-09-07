# The happy path to learn Github Actions ☀️.


What this tecnology does is to help you automate tasks within your software development lify cycle. Since this one is focused on event-drive, which means that the procedures are triggered by external events ( Pull Request, Push, API Call, and so on).

<p align="center">
  <img src="https://docs.github.com/assets/images/help/images/overview-actions-design.png"/>
</p>


_Basic structure_.


`name :` _[optional]_

`on :`  _[push, pull requests, new issue, comments, manual, schedule]_.
This option is the one that determines whether the job(s) will be set out or not. You can even exclude `paths` and `branches` while checking the condition. 
To get up to speed about this configurations check out [reference](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#configuring-workflow-events) .


A job is a set of steps that execute on the `same runner` and if there are more than one job will run in parallel by default . It contains the runner or SO/Environment( `macos-latest,ubuntu-latest,window-latest`) where everything is performed and the necessary. Here we can even set up conditional to decide when a job should be run even after meeting the event-driven condition by using the statement `if` right after clause.

  
    jobs:
      my-little-job:
        runs-on: ubuntu-latest


`Steps` can run commands, run setup tasks, or run an action in your repository, a public repository, or an action published in a Docker registry.  The basic use of this feature is focus on running a single command, however, there is a marketplace where you can find some public actions that has been developed by others and we can take advantange of them by using `uses`.

      steps:
      - name: Echoing values
        uses: actions/checkout@v2
        run : echo "NietoL"

The public actions can be found on [Marketplace](https://github.com/marketplace?type=actions).

Also one appealing feature is the `strategy.matrix` that enables you to generate multiple jobs but changing some attributes on runtime.


