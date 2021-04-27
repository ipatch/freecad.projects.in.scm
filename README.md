my first experiment with version controlling freecad project files

## workflow / 20 apr 2021

- setup a working dir, init a git repo within the working dir `git init`
- launch freecad, create a new document, save the document

  > a `project.FCStd` file will be created in the git repo

- make a change to the document, ie. add a cube or something (part workbench)
- save the document again, a `project.FCStd1` file will be created
- checkin in changes, make a commit with a quick message explaining the changes

  ```shell
  git add .
  git commit -m "checkin initial freecad projects"
  echo "optional, push to remote git repo"
  ```

## limitations

- if/when reverting a project to a prior commit within the git repo

  ```shell
  git checkout [HASH_OF_COMMIT]
  ```

...and if the current freecad file is open in freecad, the **file will not be updated!**

- close the current file, and reopen the file, and freecad should pickup the file as it existed at that particular commit.

the freecad file will have to be open/closed each time when reverting the file a particular commit.

## todos

<a name="todos"></a>

- [ ] present some modal/dialog for inputting a **commit** message when _file > save_ is run from within the freecad GUI
- [ ] close/reopen file when reverting/changing to a particular commit within the project history

## references

- [version controlling freecad files, blog post][ul1]
- [**forum.freecadweb.org** version control support (git) for freecad project files][ul2]
- [**gitlab.com** freecad wrapper around `.FCStd` project files][ul3]
- [**apple.stackexchange** useful question about using applescript as a wrapper for cli commands, ie launch window/dialog][ul4]
- [**howtoforge.com** zenity gui wrapper for cli, cross-platform][ul5]
- [**stackoverflow** using git to manage **zip** files][ul6]


[ul1]: <https://blog.lambda.cx/posts/freecad-and-git/>
[ul2]: <https://forum.freecadweb.org/viewtopic.php?f=10&t=38353>
[ul3]: <https://gitlab.com/frc-team-4739/ffos/fc-git>
[ul4]: <https://apple.stackexchange.com/questions/239764/how-can-i-run-a-shell-script-that-prompts-for-user-input-from-within-applescript>
[ul5]: <https://www.howtoforge.com/how-to-display-gui-dialogs-in-bash-script-using-zenity/>
[ul6]: <https://stackoverflow.com/questions/8001663/can-git-treat-zip-files-as-directories-and-files-inside-the-zip-as-blobs>
