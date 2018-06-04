# General information
This repository contains an overview of the tools and the technologies we are using for the summer internship projects.

**Technologies used:**

* [C# (language)](https://docs.microsoft.com/en-us/dotnet/csharp/quick-starts/)
* [.NET (framework/platform)](https://stackify.com/net-ecosystem-demystified/) 
* [Xamarin (mobile)](https://docs.microsoft.com/en-us/xamarin/cross-platform/)
* [Angular (web apps)](https://angular.io/)

**Tools used:**

* [Slack (irc/chat)](http://dualog.slack.com/)
* [Git (version control)](https://guides.github.com/introduction/git-handbook/)
* [GitHub (code reviews)](https://guides.github.com/introduction/flow/)
* [Visual Studio Code (editor)](https://code.visualstudio.com/)
* [Waffle (project management)](https://waffle.io/)
* [Visual Studio AppCenter (CI/CD)](https://docs.microsoft.com/en-us/appcenter/)
* [Visual Studio 2017 Community Edition (IDE)](https://docs.microsoft.com/en-us/visualstudio/releasenotes/vs2017-relnotes) 

## Getting started
If you are familiar with some of the tools/technologies, that's great. If not, start skimming through the links under "general information".
Second, consider installing Windows 10 on your machine as Dualog is heavily connected to the .NET / Microsoft ecosystem. Having a decent Mac with VS Code and VS 2017 for Mac installed will get you far, too.

## Company guidelines
Some standards that we (try) to follow within the Organization. This is to keep the development process somewhat streamlined.

### Colors / Design
Stuff on mimer, link to color palette?

### Coding conventions
Coding conventions create a consistent look to the code, so that readers can focus on content, not layout. They enable readers to understand the code more quickly by making assumptions based on previous experience. They also facilitate copying, changing, and maintaining the code.

To achieve this we are using an EditorConfig inside each project. [EditorConfig](https://editorconfig.org) helps developers define and maintain consistent coding styles between different editors and IDEs. The EditorConfig project consists of a file format for defining coding styles and a collection of text editor plugins that enable editors to read the file format and adhere to defined styles. EditorConfig files are easily readable and they work nicely with version control systems.

[See this link for .NET coding convention settings examples for editorconfigs.](https://docs.microsoft.com/en-us/visualstudio/ide/editorconfig-code-style-settings-reference)

### Commit naming
All Git Commit Messages should meet the following text format:
```
Subject line
(One newline)
Message Body
(One newline)
Ref <###>
```

#### Rules
1. Capitalize the Subject.
2. Do not end the Subject line with a period.
3. Message Body should end with at least one issue tracking reference.
4. Use valid MarkDown in the message body.
5. Use the present tense ("Add feature" not "Added feature").
6. Use the imperative mood ("Move cursor to..." not "Moves cursor to...").
7. Use the message body to explain what and why vs. how.

*Refer to an issue describing the bug when fixing bugs.*

### Branch naming

*Info: Master and development branches will be protected, so you can't push directly to them*

| Naming                            | When to use?                   |
| ----------------------------------| ------------------------------ |
| `feature/awesome-branch-name`     | When developing a new feature  |
| `bugfix/awesome-branch-name`      | When fixing a bug              |
| `hotfix/awesome-branch-name`      | When fixing an urgent bug      |
| `docs/awesome-branch-name`        | When updating documentation    |
| `tooling/awesome-branch-name`     | When changing tooling          |
| `performance/awesome-branch-name` | When improving performance     |
| `refactoring/awesome-branch-name` | When refactoring code          |
| `cosmetic/awesome-branch-name`    | When improving UI/Cosmetic     |
| `testing/awesomest-branch-name`   | When adding tests              |

### Development workflow
#### Starting
When creating a new feature, you should branch off from `development` and create your own branch.
E.g.
```shell
git checkout development
git pull
git checkout -b feature/awesome-new-feature
```

#### While working
Try to commit your changes as you go, but commit with logical steps. This will make it easier when team-members are reviewing your code.

```shell
git add relevant-code
git commit -m "Nice commit message that follows commit-message rules"
```

If others have pushed changes to the `development` branch you can apply those changes to your branch by rebasing the branch into yours and solve any eventual conflicts locally. (`git checkout feature/awesome-new-feature && git rebase development`)

#### When pushing changes
If you have multiple commits and you are not pleased with their commit messages, now is a good time to stop and fix these things. Rebase your own branch by `git rebase -i HEAD^n` going `n` commits back and you'll be able to edit, squash or fixup your commits before pushing. If only the last commit message is unsatisfactory you can just use `git commit --amend`.
Push your changes to GitHub by 
```shell
git push -u origin feature/awesome-new-feature
```
or simply `git push` if you're already tracking a remote branch.

You can now create a pull request on GitHub from your branch into `development`.

Once the branch has been merged into `development` you can delete your local branch by `git branch -D feature/awesome-new-feature`. Make sure to delete the remote branch after it has been merged. This can be done through the browser on GitHub or by using
```shell
git push -u -d origin feature/awesome-new-feature
```

## Licensing
All the repositories made in the "Dualog-Students" organization starts as open-source and licensed project by project. Dualog can at any time decide to take an open-source project and close it from the public to either hide company secrets or for protecting customers. See [https://choosealicense.com/](https://choosealicense.com/) for open-source licensing examples.
