# LAB - Class 16 | AWS: Cloud Servers

## Project: Deploy a Node.js server to AWS EC2

Deploy a simple Node.js server to EC2, using Elastic Beanstalk
- Choose a server you’ve built previously
  - Option 1: A simple API or Web Server
  - Option 2: A socket.io event Hub
  - The server should not require a database
  - Check in your server to GitHub

### Authors: Heather Holcomb | 401d53

***

### Problem Domain

- **Task 1:**

- Create a new environment, using Elastic Beanstalk from the AWS Control Panel (GUI)
- Manually deploy your application to this environment by uploading a .zip file
- **Task 2:**

- Using the same server, create a new environment using Elastic Beanstalk from your terminal
- Manually deploy your application to this environment by using eb deploy

***

### Links and Resources

- [GitHub Actions ci/cd](https://github.com/holcombheather/lab-16-server/actions)
- [Task 1: GUI Deploy ](http://beansarefun-env.eba-5axjwxcp.us-west-1.elasticbeanstalk.com/)
- [Task 2: CLI Deploy](http://beansarecool-dev.us-west-2.elasticbeanstalk.com/)

***

### Collaborators

- Referenced lecture demo for class 16 with instructor Ryan Gallaway
- Referenced [AWS docs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-getting-started.html#ebcli3-basics-open) for [debugging permissions](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.managing.security.html#using-features.managing.security.keypair) and completing task 2.
- Also referenced video and resources from [A Cloud Guru](https://learn.acloud.guru/course/certified-solutions-architect-associate/learn/21359b7a-a8b4-4d08-8e30-48623869199f/e3662bd5-361e-43a7-9afc-c2c2f5c921e2/watch) for an overview on Elastic Beanstalk and its value prop. 


***

### Setup

#### How to initialize this application
1. Clone this repo into your local environment
2. `npm init -y`
3. `npm i express dotenv`
4. Copy Code Fellows config files `cp -r ../seattle-code-javascript-401d53/configs/ .`

#### `.env` requirements

- `PORT` - 3001  (see `.env.sample`)

#### How to run this application

- `npm start` or `nodemon`

#### How to deploy via Elastic Beanstalk in the GUI

Create a User
1. Go to IAM
1. If no user exists, create one.  follow the prompts in the GUI
1. give that user permissions create group (or not).
  - permissions for lab 16: `AdministratorAccess-AWSElasticBeanstalk`
  - Additional Permissions added: `AdministratorAccess`

To manage the Access Key:
1. go to the users tab in `IAM`
1. select your user
1. notice the tabs:  `Permissions | Groups | Tags | Security credentials`
1. select `Security credentials`
1. create an access key.  yes a CLI access key
1. note: once created, you will not be able to view the secret key again
1. go to the terminal
  1. run the command  `aws configure`.  follow instructions... basically
  1. paste in your access key. press enter
  1. paste in your secret key. press enter.
  1. select your region
  1. default output leave as is

Your Server Code
1. confirm that your package.json is in order.
1. `main` should be assigned the appropriate file name as an entry point
1. start script should be present and also point to your file entry point
1. zip ONLY the necessary files for GUI deployment. class example:  `package.json` and `server.js`

To deploy via elastic beanstalk in the GUI
1. Go to Elastic beanstalk in console (use search bar or recently visited)
1. select the orange create application button
1. name your application (unique to your account)
1. platform, select node.js
1. platform branch, use default of node 18
1. platform version use default provided
1. no need to add tags
1. select `Upload your code`
1. confirm you have a zip file with ONLY package.json and your code.
  - NO node modules or package-lock.json
1. choose file and upload
1. you are done making selections, click the  orange `create application` button

#### How to deploy via Elastic Beanstalk in the CLI

1. `eb init`
  1. use default names, select region, no need to add SSH
1. `eb create`
  1. use default names, select region, no need to add "extras" with thee y/n questions
1. that's it.  note: create ALSO deploys code
1. if you need to update your code, run `eb deploy`

#### Features

N/A

#### Tests

N/A

#### UML

N/A
