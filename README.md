OpenScadScriptAnalyzer
===
OpenScadScripAnalyzer is an app runtime based on node.js. You can download things(scad files) from [www.thingiverse.com](www.thingiverse.com) and parse them with OpenScadScriptAnalyzer. This project is published on the [Docker](https://www.docker.com/) also.

###How to install

1 Update Sources

	$ sudo add-apt-repository ppa:chris-lea/node.js
	$ sudo apt-get update


2 Install Git

	$ sudo apt-get install Git


3 Install nodejs

	$ sudo apt-get install nodejs


4 Install docker

	$ sudo apt-get update
	$ sudo apt-get install docker.io


5 Install npm

	$ sudo apt-get install npm


6 Install bower

	$ sudo npm -g install bower


7 Clone project

	$ git clone https://github.com/jiyoungParkKim/openScadScriptAnalyzer.git
	$ cd openScadScriptAnalyzer/


8 Install project

	$ sudo npm install
	$ bower install


9 Get database

	$ sudo docker pull jiyoungparkkim/mongodb_base:0.1


10 Start mongoDB

	$ sudo docker kill $(sudo docker ps -a -q) && sudo docker rm $(sudo docker ps -a -q) && sudo docker run --name db -d jiyoungparkkim/mongodb_base:0.1

11 Get the ip adress of the mongoDB server

	$ for i in $(sudo docker ps -q); do ip=$(sudo docker inspect --format="{{ .NetworkSettings.IPAddress }}"" $i) done ;

10 Edit [openScadScriptAnalyzer/server/config/environment/developement.js]

	Change url to : mongodb://$ip/openscadanalyzer-dev

11 Start server

	$ sudo npm start
