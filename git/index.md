# Git Style Guide #


## Commit Messges ##

We are experimenting with the [AngularJS commit message conventions][ng-commit-docs]. For now, we are only using [`type`][ng-commit-type]. Conventions are enforces via the `commit-msg` git hook.

All messages must be prefixed with a `[<type>]:` from the following list:

  
  - **feature**: Adding a new feature.

    example: `[feature]: Add loop option to carousel module.`
    
  - **fix**: Bug fixes.

    example: `[fix]: Clear float on <nav> in small viewport. Fixes CFDP-101`
    
  - **docs**: Updates to documentation.

    example: `[docs]: Add links to each library/framework listed.`
    
  - **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)

    example: `[style]: Add space before and after parentheses for anonymous functions.`
    
  - **refactor**: A code change that neither fixes a bug nor adds a feature

    example: `[refactor]: Use a forEach loop instead of a for loop.`
    
  - **test**: Adding test cases.

    example: `[test]: Add tests for loop option in carousel module.`
    
  - **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation

    example: `[chore]: Add mocha HTML reporter for Bamboo reports artifact.`
    
  - **wip**: Intermediate commits (work-in-progress) related to one of the above.

    example: `[wip]: Return early if if no cache was found.`



## Branch Naming Conventions ##

  - **feature/<name>**: New features.

  - **docs/<name>**: Additions and updates to documentation. This is only required if the changes warrant a review before being merged. Otherwise, they can be committed directly to the `master` branch.

  - **release/<vX.X.X>**: Code releases. Must contain full version number (Major.Minor.Patch).

  - **review/<name|CFDP-XXX>**: Code reviews. Must use Jira ticket ID. Use if major refactoring is required to illustrate/inform feedback during a code review of another branch. Use the same name as the branch being reviewed, unless there is an existing task/story in Jira.

  - **bugfix/<CFDP-XXX>**: Fixes on unreleased branches. Must use Jira ticket ID.

  - **hotfix/<CFDP-XXX>**: Fixes for production code. Must use Jira ticket ID.



## Branching Model ##

TODO



## Release Process ##

TODO



[ng-commit-docs]: https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#commit-message-format
[ng-commit-type]: https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#type


