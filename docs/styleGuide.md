# Style Guide


## Formatting 

- Always use **Prettier** prior to committing changes, so that all files have a consistent style
    - Prettier will be installed as it is included in `package.json` (VS Code extension is not required)
    - Run `npx prettier . --write` in the project root to run on all files (or replace `.` with a specific path/file to only run on that)
- Use **LF** for newlines
- Tab using **4 spaces**
- End lines with a semicolon 



## Using Git CLI

- `git <pull | fetch> [origin]`, to get most recent changes from `origin` remote source (do **not** add another remote, `origin` should be the only remote)
- `git branch -a` to list all branches, remote and local (some duplicates might appear, regular `git branch` will only list local, will not show all branches if local repo has never seen them before)
- `git switch <branch>` or `git checkout <branch>` to switch to the given branch (can be just the branch name, don't need `HEAD` or `origin/...`)
- `git status` shows current branch, and its version status (new/changed/deleted files)
- `git add -A` to stage all changes for commit (including files that haven't been added to source control yet), `git add <file>...` to only stage certain files
- `git commit -m 'message goes here'` to commit with message (`git commit` opens default terminal editor, usually vim so try not to do that lol)
- `git commit -a` to automatically stage all changes and then commit those changes (does **not** include files that haven't been added to source control with `git add ...`)
- `git push` uploads all of the changes to online repository



## Naming and Other Conventions 

- Always use **camel case** (i.e. `camelCase`) when naming functions and variables (except for platform-specific functions, see below)
- For functions/variables relating to a specific platform, prepend the name with either `SP` or `AM` (i.e. `SPAuthorization`)
- When throwing errors, use the `errorMessage` function provided in `helpers/error.js`, so that error messages are consistent
- At the top of each module, declare the following
    ```js
    const MOD_NAME = "<file name here>";
    ```
    to make calls to `errorMessage` easier to write





## Directory Structure

Use the below graphic as a guide for where to put what files:

```
cs546-group7
├── package.json    // project config files in root
├── .gitignore
├── ...
├── config          // mongodb configuration files
│   ├── ...
├── data            // for functions that interact with the mongodb driver
│   ├── ...
├── docs            // for documentation files (like this one!)
│   ├── ...
├── helpers         // for helper functions used by other modules and in routes
│   ├── ...
├── routes          // expressjs routers
│   ├── ...
├── tasks           // npm scripts (mainly for testing, seeding db, etc...)
│   ├── ...
└── views           // handlebars layout/templating files
    ├── ...
```
