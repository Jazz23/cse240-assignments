# For anyone who wants to use a Devcontainer/GitHub Codespace

> This repo is to help those struggling with setup on their local machines. This repo automatically installs autograder and python for you, without needing to install anything (besides docker) on your local machine. You can also setup a "GitHub Codespace" which is a devcontainer in the cloud, which literally only requires **a browser** to connect to (you can also connect via a local VSCode instance).

> Start by clicking **"Use this template > Create new repository"** to make a *copy* of this repo to your personal account. Don't forget to mark visibility as private. 


### For local dev container (docker required):
* Make sure VSCode has the "Dev Containers" extension installed.<br>
* After cloning **your _private_ repo copy** to your local machine, create a `.env` file in the root of the repo that looks like<br>
> EMAIL=youremail@ucsc.edu<br>
> PASSWORD=yourpasswordyougotemailed<br>

* *After* you've made your `.env` file, re-open the folder in the dev container (either by the popup or VSCode command)

### For GitHub Codespace (free remote dev container in cloud):

* Edit the file `.devcontainer/devcontainer.json` on GitHub.com. Remove `--run-args` section of `.devcontainer.json`.
* Open repository settings
* Near the bottom, click **Secrets and Variables > Codespaces** and add<br>
> EMAIL=youremail@ucsc.edu<br>
> PASSWORD=yourpasswordyougotemailed<br>
* Go back to the main page on the repo, click **Code -> Codespaces -> Create codespace on main**
* You will get a warning once in the codespace, just ignore it

## Once you've setup your devcontainer/codespace, use the following pattern for autograder commands:

> python3 -m autograder.run.submit --user $EMAIL --pass $PASSWORD <AssignmentPath.ipynb>

Happy coding!

(P.S. if all that setup is a pain, just hard code your credentials in `config.json` and skip all the env stuff :D)


<br>
<br>
<br>
<br>

# Assignments
These are the assignments for CSE240 at UCSC.  They are:
- [Assignment1](Assignment1/)
- [Assignment2](Assignment2/) (NOTE: Assignment2 will be submitted to CANVAS not the autograder).
- [Assignment3](Assignment3/)
- [Assignment4](Assignment4/)
  
# Installing the Autograder package
Install the autograder with `pip3 install autograder-py` on the command line.  

# Submitting and using the Autograder in CSE 240

Make sure that the autograder is installed on your local machine by
typing: `python3 -m autograder.cli`.  If you see the `--help` option:

```nil
python -m autograder.cli
The autograder CLI package contains several tools for interacting with the autograder.
The following is a non-exhaustive list of CLI tools.
Invoke each command with the `--help` option for more details.
```
## Using the autograder

The autograder command line interface (cli) is [documented](https://github.com/eriq-augustine/autograder-py).  As a
student in the class, the main commands you will use are:

-   `python3 -m autograder.run.submit`: this will submit an assignment
    for a particular class and assignment.
-   `python3 -m autograder.run.peek`: this will show you your last submission
-   `python3 -m autograder.run.history`: this will show a summary of all
    your past submission
