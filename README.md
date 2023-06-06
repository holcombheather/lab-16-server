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
- [Task 1 ](http://beansarefun-env.eba-5axjwxcp.us-west-1.elasticbeanstalk.com/)
- [Task 2]()

***

### Collaborators

- Referenced lecture demo for class 12 with instructor Ryan Gallaway
- Reference lecture code review in class 13 with instructor Ryan Gallaway
- Consulted TA Keleen for help on feature for clients joining rooms.
- Used AI to help write tests using a template I authored by referencing the tests from the lecture above and modifying it to my needs.


***

### Setup

#### How to initialize this application
1. Clone this repo into your local environment
2. `npm init -y`
3. `npm i jest chance eslin socket.io socket.io-client`
4. Copy Code Fellows config files `cp -r ../seattle-code-javascript-401d53/configs/ .`

#### `.env` requirements

- `PORT` - 3001  (see `.env.sample`)

#### How to run this application

- `npm start` or `nodemon`

#### Features

CAPS Phase 1: Event Driven Applications
- As a vendor, I want to alert the system when I have a package to be picked up.
- As a driver, I want to be notified when there is a package to be delivered.
- As a driver, I want to alert the system when I have picked up a package and it is in transit.
- As a driver, I want to alert the system when a package has been delivered.
- As a vendor, I want to be notified when my package has been delivered.
- As a developer, I want to create network event driven system using Socket.io so that I can write code that responds to events originating from both servers and client applications

#### Tests

To run tests, use the command `npm test` in your terminal

 PASS  clients/vendor/vendor-handler.test.js
  Vendor Handler
    ✓ emit pickup message and vendor order payload (3 ms)
    ✓ log delivered message and emit vendor thank you payload

 FAIL  clients/driver/driver-handler.test.js
  Driver Handler
    ✕ log pickup message and emit in-transit payload (1 ms)
    ✕ log confirmation message and emit delivered payload (1 ms)

#### UML
![UML image](UML_lab11.png)
