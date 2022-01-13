# Introduction to curriculum
Overview of what the weeks look like and approach to lectures

## Sources
[Lecture Video](https://vimeo.com/664898047/6e11d946c0)

[Teacher Notes](https://github.com/DominicTremblay/w1d2-lecture/tree/demo-east-jan10-2022)

[Teacher Demo](https://github.com/DominicTremblay/w1demo_jan10)

## Week 1
###### FOCAL: Functions objexts conditionals arrays and loops

- FF: Prog test, recursion

## Week 2
###### Async control flow (callbacks and promises) Netwrooking HTTP API NPM Packages

- FF: Prog tesst 2 and OOP

## Week 3
###### First web app with HTTP Servers, express.js, cookies, basic html and forms

- ff prog test and data structures: trees

- TinyApp - url shortner

- Tech interview

## Week 4
- Front end: css Browsers jquery ajax css html

- ff algo complexioty and test

- Tweeter - Twitter Clone

## Week 5
###### Databases

- FF SQL test and midterm kickoff


## Week 6
###### Define real world situations
- Proj managemnet
practice fundamentals
define teams, stack, and reqs

- FF: Demo to peers AND CAREER / RESUME Prep

- More details INC on week 5

## Week 7-10
###### Mordern web stacks
- single page
realtime apps wiuth web sockets
automayed testing
class based/oop with ruby
ruby
maintaining code

- FF: Research reflectr and write

## Week 7-8
- Interview Scheduler (React)

## Week 9
- Tech interview

## Week 9-10
- Jungle - (Rails; not evaluated) (Is an app?)


# Approach to lectures
- Lectures are about new things
  - So focus on it 100%


# Tools
- VSCode
- Git (Version control)
  - Repos
  - Save milestones
  - Keeps a history of code
  - Backups code to github
  - Used to work with teams
  - cmds
    - ```git log```
      - history of commits
    - ```git add .```
      - adds all changed files to staging area
    - ```git remote```
      - ```git remote add origin <SSH:URL.git>```
        - adds push/fetch url to local repo
      - ```git remote rm origin```
        - removes push/fetch URL from local repo
      - ```git remote -v```
        - Shows remote URLS for fetch/push
    - ```git branch```
      - gets list of all branches of repo
      - ```git branch -M main```
        - renames branch to main
    - ```git push```
      - ```git push -u origin main```
        - ```-u``` flag sets default branch for use with ```git push```
    - ```git clone <URL.git>```
      - copies repo files to current folder 

# Demo Code Section
###### Sum all command arguments into a number: Sum.js

### Methodology
- Isolate main programs purpose
  - Sum all number inputs and output it
- Identify Edge cases
  - Must be num
  - must take atleast 2 args
- Functions should have a single responsibility
  - function sum should only sumits inputs and do no input validation

### Implementation
1. build main purpose
2. Bugfix (if any bugs)
3. Then modify to support edge cases
4. Bugfix (if any bugs)
5. now we Refactor
6. Bugfix (if any bugs)

### new things learned for JS
- ```Array.slice```
  - can take negative numbers to go from back to front
  - IE: ```Array.slice(-1)``` gets the last value of the array
- How to stop a script
  - ```return;```
    - Reserved for functions (Usually)
  - ```process.exit()```
    - better to use for functionless scripts
    - Or to completely exit an application from within a function
      - like incase of errors