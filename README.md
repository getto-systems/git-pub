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

- [Requirements](#requirements)
- [Usage](#usage)
- [License](#license)


<a id="requirements"></a>
## Requirements

- GNU bash, version 4.3.48(1)-release (x86_64-alpine-linux-musl)
- git version 2.14.2


<a id="usage"></a>
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

cleanup current-branch from remote and local

```bash
git purge #=>
  git push pub :<CURRENT_BRANCH> &&
  git branch -d <PARENT_BRANCH> &&
  git branch <PARENT_BRANCH> origin/<PARENT_BRANCH> &&
  git checkout <PARENT_BRANCH> &&
  git branch -d <CURRENT_BRANCH> &&
  git pub
```

- `CURRENT_BRANCH` : working branch name
- `PARENT_BRANCH` : base branch of working branch

1. delete pub's current-branch
1. renew parent-branch : delete local, and create from origin
1. checkout parent-branch
1. delete local current-branch
1. push pub

### git parent

detect base branch of current-branch

```bash
git checkout master
git checkout -b branch-A
git commit -m "some changes"

git parent # => master
```

```bash
git checkout master
git checkout -b branch-A
git commit -m "some changes"
git checkout -b branch-B
git commit -m "some changes"

git parent # => branch-A
```

### git reg-pub

register remote that named 'pub'

```bash
git reg-pub github:GITHUB_USER bitbucket:BITBUCKET_USER #=>
  git remote add pub $URL
```

### git delete-pub

delete current-branch from remote that named 'pub'

```bash
git delete-pub #=> git push pub :<CURRENT_BRANCH>
```

<a id="license"></a>
## License

git-pub is licensed under the [MIT](LICENSE) license.

Copyright &copy; since 2016 shun.fix9@gmail.com
