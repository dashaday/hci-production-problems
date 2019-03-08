## Working in Groups with Git

*Disclaimer: I'm not an expert at git, this is simply a written guide patterned after Prof Stolley's lecture from March 4. I just thought it could help people remember what to do*

After creating an organization and group repository, these are the things you gotta do.

**Forking**
1. Click Fork from your organization's group repo
   - you'll be redirected to your own forked repository.
2. Click Clone or Download from forked repo
   - copy link
   - `git clone [your-clone-link]`
3. Add Remote link
   - copy clone link from group repo
   - go into local copy of repo
   - `git remote add group [group-repo-clone-link]`
   - to check: `git remote -v`

**Editing on your Own Branch**
1. Open and make edits on file as usual
2. Make branch (per feature)
   - `git checkout -b branch-name`
3. Git add and commit as usual
4. Push
   - `git push origin branch-name`

**Updating/ Merging to Group Repo**
To push your edits:
1. Go to group repository
2. Click Create Pull Request

To check other's pull requests:
1. Go to group repo -> pull requests
2. Click on the earliest commit
3. Comment notes and edit if necessary
4. Merge pull request when unanimous LGTM (looks good to me)

**Update Local Files/ Conflicting Pull Request**
if a message appears that branches can't automatically merge:
1. Add comment on error + Click Create Pull Request
2. Resolve Conflicts Locally (don't click the Resolve button on GitHub)
   - `git checkout master`
   - `git pull group master`
   - `git push origin master`
   - `git checkout branch-name`
3. Rebase
   - `git rebase master`

if failed merge:
1. Manually edit
   - open updated file and manually edit on atom
2. Complete rebase
   - `git add [filename]`
   - `git rebase --continue`
3. Push
   - `git push origin [branch-name]`
   - !ERROR will occur but it's okay
   - `git push origin [branch-name] -f`
