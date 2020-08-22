## What is Jenkins??

- Open source automation server with many plug-ins to support the automation of different development tasks
- Allows a simple way to set up CI/CD environment for most languages & source code repositories using pipelines, as well as automating other routine development tasks
- Gives you a faster & more robust way to integrate chain of build, test & deployment tools

## How does Jenkins works?

![image](https://www.guru99.com/images/1/063018_1012_WhatisJenki1.jpg)

## What is an API call?
- The moment you add an endpoint to an URL & send request to serve, this counts as making API call
- E.g. logging into an app, asking google a question
- Takes place when you send a request after setting up your API with correct endpoints
- Information is transferred, processed and feedback is returned back

## API
- Application Programming Interface
- Part of the server that receives requests and sends responses
- Set of protocols, procedures and tools that allow interaction between two applications
- Software intermediary that delivers requests to the serveer and relays a response back to the client
- They speed up creation process of software applications --> make frequently repeated yet complex processes reusable allowing developers to skip steps when creating code

## Acceptance Criteria
- [x] Code is checked from the develop branch and not the master branch and pushed to master branch once code is successful

- [x] The git publisher plugin pushes the master branch once tests pass

- [x] Email is sent to develop once the code merges successfully 

## Creating new item on Jenkins

1. New item 
2. Add name
3. Add decription e.g. 

`This is a CI job for our node.js sample web app`

4. Select `discard old builds` & set `max # of builds to keep` as 3

![image](https://github.com/ugneokmanaite/webapp_ci/blob/master/images/general.JPG)

5. Select ` restrict where this project can be run` select sparta-ubuntu-node

![image](https://github.com/ugneokmanaite/webapp_ci/blob/master/images/build_environment.JPG)

6. Add Github project and add project repo url

7. Under Office 365 Connector at the top tap, follow the instructions and set up a webhook in email(follow instructions in link)
![image](https://github.com/ugneokmanaite/webapp_ci/blob/master/images/email.JPG)

### Source Code Management
8. Add Repository url - This is the SSH url available inside the project repo under ` clone ` button

![image](https://github.com/ugneokmanaite/webapp_ci/blob/master/images/source_code_management.JPG)

For branch to build: in order to check from develop branch change this to `*/devevlop`

9. Create a new SSH [click here for directions](https://github.com/ugneokmanaite/ci-start-code) 

NOTE: enter public in Github and private in Jenkins

10. In Jenkins click `add` under credentials.
11. Under `kind` choose `SSH Username with private key`
12. Copy and paste the generated private key
13. Add the public key of this to Githubs project repo
    
14. Under `Build` and execute shell enter the following command
![image](https://github.com/ugneokmanaite/webapp_ci/blob/master/images/execute%20shell.JPG)

16. For Post-build Actions select the following: 

![image](https://github.com/ugneokmanaite/webapp_ci/blob/master/images/post-build-actions.JPG)

17. Go back to Github project repo- settings- web hooks 

18. paste the link of server path and add the following on the end `/github-webhook/`

19. To check if its automated & web-hook works add changes in bash terminal, commit these changes & push. This should push into Github & then test in Jenkins- showing whether the test has passed or failed


** Problems were occuring so seed folder was commented out **



NOTE: Make sure to create a develop branch in your repo for this 

in bash termina

`git pull`

`git checkout develop`- to switch to the different branch