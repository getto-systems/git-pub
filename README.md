# git-pub

push, delete, purge remote public branch

## Usage

```bash
git pub
# git push pub $(git current)
```

```bash
git delete-pub
# git push pub :$(git current)
```

```bash
git purge
# git push delete-pub
# git push checkout master
# git push pull
# git push branch -d $branch
```

```bash
git reg-pub github:GITHUB-USER bitbucket:BITBUCKET-USER
# git remote add pub URL
```

## Installation

```bash
git remote add pub 'URL'
```
