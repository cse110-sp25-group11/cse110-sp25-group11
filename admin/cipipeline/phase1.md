# Phase 1 Pipeline Status
## Code Quality  + Linting
Firstly, we use curl to install qlty to use as our linting software. (NOTE: need Ubuntu on Windows, currently working on a workaround. Current solution is having windows users push changes to remote, pull them on wsl and then run qlty)
Then qlty init inside the repo and install the plugins. Run the following command:
```
curl https://qlty.sh | sh
```
Then go into the repo and run:
```
qlty init
```
We chose qlty because it does code linting and quality checking from the command line in a very intuitive way. We are working on more potential configurations in the future. It has commands such as `qlty metrics --all --max-depth=2 --sort complexity --limit 10` and `qlty check` that are easy to use and give us the detials we want about our code before we move it further down the pipeline.

## Unit Tests
We currently have basic unit tests setup in the repo, with the infrastructure in place for more tests to be added as we get deeper into development. We are using the Jest library. 

## Auto Docs
We have jsdoc setup to create a site that automatically has our documentation based on the comments on our code. Some further testing and configuration of this feature might be required down the road as we continue to develop this project

## PR template
We created a pull request template to make sure all team members document the changes in their pull request. 

## Code review template
Our team also has a template that the two code reviewers must fill out before approving

## Merging changes
All unit tests/other checks must pass and 2 reviewers must have approved before merging can happen.
