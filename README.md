OpenScadScriptAnalyzer
===
OpenScadScripAnalyzer is an app runtime based on node.js. You can download things(scad files) from [www.thingiverse.com](www.thingiverse.com) and parse them with OpenScadScriptAnalyzer. This project is published on the [Docker](https://www.docker.com/) also.


Update Sources

	$ sudo add-apt-repository ppa:chris-lea/node.js
	$ sudo apt-get update


Install Git

	$ sudo apt-get install Git


Install nodejs

	$ sudo apt-get install nodejs


Install docker

	$ sudo apt-get update
	$ sudo apt-get install docker.io


Install npm

	$ sudo apt-get install npm


Install bower

	$ sudo npm -g install bower


Clone project

	$ git clone https://github.com/jiyoungParkKim/openScadScriptAnalyzer.git
	$ cd openScadScriptAnalyzer/


Install project

	$ sudo npm install
	$ bower install


Get database

	$ sudo docker pull jiyoungparkkim/mongodb_base:0.1


Start mongoDB

	$ sudo docker kill $(sudo docker ps -a -q)
	$ sudo docker rm $(sudo docker ps -a -q)
	$ sudo docker run --name db -d jiyoungparkkim/mongodb_base:0.1

Get the ip adress of the mongoDB server

	for i in $(sudo docker ps -q); do     
  	ip=$(sudo docker inspect --format="{{ .NetworkSettings.IPAddress }}"" $i)
done ;

Edit [openScadScriptAnalyzer/server/config/environment/developement.js]

	Change url to : mongodb://$ip/openscadanalyzer-dev

Start server

	$ sudo npm start
