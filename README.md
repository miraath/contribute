# Contribution to miraath repository

## Setting up our Style Guides (linters) in new project :

* [Javascript Style Guide](javascript.md)
* [SCSS Style Guide](scss.md)
* [Typescript Style Guide](typescript.md)

## Contributing on github

We will use "[A successful branching model](http://nvie.com/posts/a-successful-git-branching-model/)" without the release branch.

### Quick cheatsheet (taken and modified from [the model](http://nvie.com/posts/a-successful-git-branching-model/))

#### Branching
```bash
#create the branch
git checkout -b myfeature develop
# push the branch to github repo
git push -u origin myfeature
```
Then, make a pull request on github

After merging the pull request, we should delete the branch via github.

Manual merge (**for repo admins only !**)
```bash
git checkout develop
git merge --no-ff myfeature
git branch -d myfeature
git push origin develop
```

#### New Release (**for repo admins only !**)
```bash
git checkout develop
# Change version number in corresponding files
git commit -a -m "Bumped version number to 1.2"
git push origin develop
# Finishing a release branch
git checkout master
git merge --no-ff develop
git tag -a 1.2
git push origin master
```

#### hotfix branch
```bash
# Creating the hotfix branch
git checkout -b hotfix-1.2.1 master
# Change version number in corresponding files
git commit -a -m "Bumped version number to 1.2.1"
# Correcting the bug
git commit -m "Fixed severe production problem"
# push the hotfix on github
git push -u origin hotfix-1.2.1
# Make a pull request on github tagged "bug"
```

#### Finishing the hotfix branch (**for repo admins only !**)
```bash
git checkout master
git merge --no-ff hotfix-1.2.1
git tag -a 1.2.1
# Include the bugfix in develop
git checkout develop
git merge --no-ff hotfix-1.2.1
# Remove the hotfix branch
git branch -d hotfix-1.2.1
```
