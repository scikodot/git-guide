# Git Guide
A set of commands and operations I always forget.

## Force pull from remote (removes all local changes)
```
git fetch <remote>			Pull from remote without merging
git reset --hard <remote>/<branch>	Reset local repo state to match the state of the remote
```
## Clean commit history
```
git rebase -i <commit_to_start_from> -X<strategy>	Interactive rebasing of all commits,
							starting from the specified commit, 
							then merging commits back in the branch
```
The following options might be useful when ordering commits in the editor:
```
reword (r)	Change message of the commit (should be changed when the editor opens 
		another time, not right there)
fixup (f)	Squash commit to the previous one, discarding its own message
```
After rebasing, the local repo can be pushed to its remote:
```
git push <remote> <branch> -f	Force push local repo to remote, totally rewriting 
				the remote's history with the local one
