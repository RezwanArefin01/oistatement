# OIStatement
Based on [IOI-Translation](https://github.com/ioi-2019/ioi-translation) system, a lightweight tool to build pdf from markdown. Intended to be used in preparation of OI-styled statement. 

# Installation:
1. Clone the repository. 
2. Add the directory oistatement to your `PATH` variable.  
3. Have either `chrome` or `brave` available.
4. For Arch based distros, install the following packages from AUR: `cpdf`, `ttf-ms-fonts`.
    - For other distribution, you need to figure out the equivalent.
5. Install the python package: `jinja2`.
6. Now you should be able to compile the given test markdown file with `oistatement english.md`. 

# Usages 
Change `static/img/logo.svg` acording to your needs. 

Write statement in `statement.md` and put `statement.json` in the same directory (both should have same name exclusding the extension). The format of `statement.json` is: 

```
{
    "task_name": "task-code-name",
    "language": "English/Bengali", 
    "contest": "contest day"
}
```
Then you can make the pdf with `oistatement statement.md` 