# Learn github actions

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
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
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