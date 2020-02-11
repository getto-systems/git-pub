# git-pub

push current-branch to remote

```bash
git commit -m "some changes"

git pub

# pull request ...
# and merged

git purge
```

###### Table of Contents

- [Requirements](#Requirements)
- [Usage](#Usage)
- [License](#License)


## Requirements

- GNU bash, version 4.3.48(1)-release (x86_64-alpine-linux-musl)
- git version 2.14.2


## Usage

to install git-pub, clone into your bash-scripts directory, and export PATH

```bash
INSTALL_DIR=path/to/scripts/git-pub

git clone https://github.com/getto-systems/git-pub.git $INSTALL_DIR

export PATH=$INSTALL_DIR/bin:$PATH
```


### git pub

push current-branch to remote that named 'pub'

```bash
git pub #=> git push pub <CURRENT_BRANCH>
```


### git purge

1. check current branch is fully merged into parent branch
1. checkout parent branch
1. delete current branch


### git parent

detect base branch of current-branch

```bash
git checkout master
git checkout -b branch-A
git commit -m "some changes"

git parent # => master
```


### git parent-sync

fetch origin, then rebase `origin/$parent`


### git wipe-widow-branch

delete branches that upstream is already deleted

```bash
git fetch --prune
git wipe-widow-branch
```



### git reg-pub

register remote that named 'pub'

```bash
git reg-pub github:GITHUB_USER bitbucket:BITBUCKET_USER #=>
  git remote add pub $URL
```


## License

git-pub is licensed under the [MIT](LICENSE) license.

Copyright &copy; since 2016 shun.fix9@gmail.com
