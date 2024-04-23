# Learn github actions

[![Learn github actions](https://github.com/ishxiao/learn-github-actions/actions/workflows/learn-github-actions.yml/badge.svg)](https://github.com/ishxiao/learn-github-actions/actions/workflows/learn-github-actions.yml)

1. Create a new repository.

- Create a directory named `learn-github-actions` to contain the project.

- Go into the new directory.

- Type `git init`.

- Create a file named `README.md`.

- Type `git add` to add the file.

- Type `git commit`.

2. In your repository, create the `.github/workflows/` directory to store your workflow files.

3. In the `.github/workflows/` directory, create a new file called `learn-github-actions.yml` and add the following code.

```
name: Learn github actions
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v4
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
```

4. Commit these changes and push them to your GitHub repository.

5. Connect it to github.

You’ve now got a local git repository. You can use git locally, like that, if you want. But if you want the thing to have a home on github, do the following.

- Go to github.
- Log in to your account.
- Click the new repository button in the top-right. You’ll have an option there to initialize the repository with a README file, but I don’t.
- Click the “Create repository” button.

Now, follow the second set of instructions, “Push an existing repository...”
```
$ git remote add origin git@github.com:[username]/[repo_name]
$ git push -u origin master
```

More infromation see [official docs](https://docs.github.com/en/actions/learn-github-actions).