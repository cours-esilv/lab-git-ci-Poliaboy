[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/fqgCysTO)
# TP 1 : CI/CD

## Instructions
Answers to the questions in this statement must be submitted as files named according to the question number in your repository, in the `answers` folder. 
Each answer will be the subject of a new file in your repo. 
> Questions requiring an answer in the form of a file will be tagged with the following icon: ⚠️ These files are corrected automatically by Github Autograde.

> Commits are not optional. Commits are not optional **Commit as soon as the statement asks you to**.

The TP must be done individually and will be based on the answers in the files in the `answers` folder, as well as on the code in your personal repositories.

## Reminders
### Git
[Official Git Documentation](https://git-scm.com/docs)
Command | Description
-- | --
`git clone` | Clone a repository on your computer
`git add` | Add files to the staging area (which will be taken into account in the next commit)
`git commit` | Create a new commit locally
`git push` | Push your local commit tree to the server (Local --> GitHub)
`git pull` | Synchronise your local tree with the remote tree (Local <-- GitHub)
`git branch` | Create a new local branch
`git merge` | Apply changes from one branch to another locally

### GitHub flow
[GitHub flow](https://docs.github.com/en/get-started/quickstart/github-flow)
![GitHub flow diagram](https://i0.wp.com/blogs.embarcadero.com/wp-content/uploads/2021/12/Github-flow-with-GitHub-actions-7803961-8145433.jpg?ssl=1)

### Pull request
![Pull request diagram](https://miro.medium.com/max/600/1*ubVyD2GaOAlSfqRNbL0Bjg.png)

### Github
* Classroom
* Issue

### Github actions
* SaaS service - [github.com/features/actions](https://github.com/features/actions)
* Pipeline: CI vs CD
* Pipeline: Configuration as code

---

## 1 : Git 

### 1.0 : Creating a Github account
Go to [Github](https://github.com/) and create an account if you have not already done so.

### 1.1 : Accept the assignment 
Follow the link on the board or in the Teams channel to get a personal copy of this repository in the GitHub Classroom organization `cours-esilv`.

### 1.2 : Clone the repository
Clone the newly copied repo on your computer 
 
### 1.3 : Make a commit 
In your repo, edit the identity.md file and fill it with your personal data (first and last name).

Commit and pushe changes made to the file
> Commits are not optional. **Commit at least as soon as the statement asks you to**.

> ⚠️ **ANSWER**: Create a file called `1.3` containing the commands you used to commit and push your changes.

### 1.4 : Browsing the logs
Display the logs of previous commits.

Bear in mind that everything has been logged since the start of the project. You can find messages, dates and also the authors of past commits.

> ⚠️ **ANSWER**: Create a file called `1.4` containing the command you used to view the logs.

### 1.5: Ginny has disappeared, I'm afraid we'll never find her!
Using the command you used in the previous question, find **Ginny** before it's too late!

> Hint**: Look in the documentation for the previous command to find ideas for other commands.

> ⚠️ **ANSWER**: Create a file called `1.5` containing **only** the command you used to track down Ginny.

### 1.6 : List the branches
List **all** the branches in the repository.

Do all the branches seem normal to you? Is there a branch that catches your eye? 
If so, check it out.

> ⚠️ **ANSWER**: Create a file called `1.6` containing the command you used to display the branches in your repo.

### 1.7 : Merge the branch
Now that you've had a look at the branch that caught your attention, merge the changes made to it into your main branch (snape -> main). Then delete the `snape` branch locally.

> ⚠️ **ANSWER**: Create a file called `1.7.1` containing the command you used to merge the `snape` branch into the `main` branch.

> ⚠️ **ANSWER**: Create a file called `1.7.2` containing the command you used to delete the `snape` branch (after merging the changes to `main`).

### 1.8: Create a branch
Now that you only have one `main` branch in your repo, create a branch from `main`. The branch you want to create should be called `feature/` followed by the first letter of your first name and then your surname in lower case (no spaces or accents in the name).

> Ex Albus Dumbledore --> feature/adumbledore

Then go to your newly created `feature/{name}` branch.

> ⚠️ **ANSWER**: Create a file called `1.8` containing the commands you used to create it, and move to the new branch.

### 1.9: Ah, that's where you would have liked to have taken the last course :trollface:
Answer the questions in the `questions.md` file, then commit the changes to the `feature/{name}` branch.
Finally, upload all the changes you've made to all the branches to your GitHub repository.

> ⚠️ **ANSWER**: Create a file called `1.9` containing the commands you used to push all the branches to your GitHub repo.

### 1.10 : Pull request time !
In the GitHub web interface, open a pull request from your `feature/{name}` branch pointing to the develop branch of your repository.

> Warning**: Don't forget to add me (laurentgrangeau) as a reviewer of your pull request so that I can correct you.

For more help on pull requests see the [official documentation](https://help.github.com/articles/about-pull-requests/)

---

#2: CI/CD with GitHub Actions
In this second part, you must use the same repo as that obtained at the end of part 1, by placing yourself on the `main` branch of your repo.

> ⚠️ **WARNING**: Each question requiring a code modification requires at least one commit and one push in your repository. The breakdown of commits is taken into account in the scoring.

> To carry out all the steps required in this part, you will place yourself on the `main` branch.

The aim of this second part of the tutorial is to implement a CI (continuous integration) pipeline to automate:
* downloading dependencies useful for building the application
* build the application 
* testing the application and making it available in a UI that can be used by anyone
* packaging the application using Docker - no pressure, I'll give you everything for the Docker part for now :ok_hand:

To do this, we're going to use a SaaS solution integrated into GitHub called **GitHub Actions**.

Thanks to its pipeline system, this solution can be used to implement the automations we want to carry out in this tutorial.

Pipelines are described in YAML (pipeline as code) code files.

For an overview of GitHub Actions features, [see the official page](https://docs.github.com/en/actions)
For more documentation on the syntax of YAML files, [see the official documentation](https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions)

**Important**: The above documentation will be essential for the successful completion of this and subsequent tasks.

### 2.1: Creating your first Pipeline - Build & Test
On the home page of your repository (on GitHub), go to the `Actions` menu and click on `set up a workflow yourself`.
This will display the YAML file corresponding to the Continuous Integration (CI) you are creating.

This file describes several essential steps in setting up a pipeline:
**triggers** (`on` keyword): Defines the conditions under which the actions described in this pipeline will be carried out.
* steps**: The description of the steps to be automated

You can now click on the `Start commit` button.

> ⚠️ **WARNING**: Don't forget to add a meaningful commit message to each commit. This will help you when you come back to the project in the future.

Observe the execution of the pipeline in the GitHub Actions UI.

### 2.2: Building our application
For the moment, the build isn't doing much apart from displaying two messages.
So we're going to modify the pipeline to build our java application.

To do this, modify the `.github/workflows/main.yml` file to add the following build steps:

```yaml
      # Installe java 8 sur l'agent
      - name: Set up JDK 8
        uses: actions/setup-java@v2
        with:
          java-version: '8'
          distribution: 'adopt'

      # Compile notre application
      - name: Build with Maven
        run: mvn --batch-mode --update-snapshots package
```

Start your changes and observe the build of your application.

### 2.3: Integrate test results
If you look closely at the build logs, you will see that unit tests are being run.
We are going to retrieve the test report and display it in the pipeline result.

To do this, modify the `.github/workflows/main.yml` file to add the following build steps:

```yaml
      # Publie les résultats de test
      - name: Publish Unit Test Results
        uses: EnricoMi/publish-unit-test-result-action@v1
        if: always()
        with:
          files: target/**/*.xml
```

Start your changes and observe the build and the results of your application's unit tests.

### 2.4: Publishing the built artifact
You are now going to publish the artifact you built in the previous steps.
This allows you to download the artifact in question and also to deploy it in later stages on different environments.

To do this, modify the `.github/workflows/main.yml` file to add the following build steps:

```yaml
      # Publie les fichiers présents dans le dossier target dans un build artifact
      - name: Upload a Build Artifact
        uses: actions/upload-artifact@v2.2.4
        with:
          name: my-app-1.0
          path: target/*
```

Commit your changes and observe the build and the artifact published on the build page.

### 2.5: Adding packaging
So far the pipeline has built and tested the application but no deployable package has been created or persisted. 
You are going to create a Docker image to make our appliance ready for use.

To do this, create a Dockerfile at the root of your project containing the following code:

```dockerfile
FROM maven:3.3.9-jdk-8-alpine

COPY target/my-app-1.0-SNAPSHOT.jar /root/my-app-1.0-SNAPSHOT.jar

CMD ["java", "-jar", "/root/my-app-1.0-SNAPSHOT.jar"]
```

Then modify the `.github/workflows/main.yml` file to add the following build steps:

```yaml
      # Installe la commande docker sur l'agent
      - name: Install Docker
        uses: docker/setup-buildx-action@v1
        id: buildx
        with:
          install: true
          
      # Build l'image Docker
      - name: Docker build
        run: |
          docker build .
```

Commit your changes one last time and observe the build of the Docker image via the logs.

### 2.6: Setting up multi-branch management
For the moment your pipeline is only triggered on the `main` branch (see trigger).

Change the value of the trigger to launch the pipeline on all branches of type:
* main
* feature (beginning with the word feature/...)

### 2.6: Creating a new branch
Your pipeline is now ready to execute the steps defined within it, whatever branches are created. 

Create a `feature/test-build` branch from the develop branch and note that the build is automatically applied to this branch.

### 2.6 : Conclusion
You can now create several features branches and see that the build, test and package stages are applied to these branches.

All this configuration means that you can have a validation system that is as close as possible without wasting time on the rapid feedback you need to improve product quality.
