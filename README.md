                         EasyMock Server Procedure


Prepared by: Ian

一. Environment Build

Github: https://github.com/easy-mock/easy-mock 


Per  Quick Start in the reference site,  we need install node.js(v8.x, v10.x is not supported ) & MongoDB (>= v3.4) & Redis（>= v4.0）.

1 Install node.js

# Using Ubuntu

$> curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -

> sudo apt-get install -y nodejs


$> nodejs -v

v8.16.0

$> npm -v

6.4.1



    Install MongoDB

Office site: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/

Reference Doc:  http://192.168.18.224:8888/svn/Microservices/Infrastructure/trunk/main_body/docs/design/MongoDB_Install.doc 

    Install Redis

Reference Doc:

http://192.168.18.224:8888/svn/microservice/ResourceService/trunk/main_body/docs/design/Redis_Install.doc 


    Install EasyMock

$> git clone https://github.com/easy-mock/easy-mock.git

$> cd easy-mock && npm install



    Config EasyMock 

Update redis password as below:

{ . . .

"redis": {

    "keyPrefix": "[Easy Mock]",

    "port": 6379,

    "host": "localhost",

    "password": "root",

    "db": 0

  },

  . . .

}


二. Run

#cd redis dir

$> cd redis-5.0.3


#start redis

$> sudo /redis-5.0.3$ sudo ./src/redis-server  ./redis.conf

# Stop

#Ctrl+c


#$> cd to easy-mock dir

# Build front-end assets

 /easy-mock$> sudo npm run build


# Run Easy Mock as production environment (You should run `build` first)

/easy-mock$> sudo npm run start

> easy-mock@1.6.0 start /opt/easy-mock

> cross-env NODE_ENV=production node app


WARNING: NODE_ENV value of 'production' did not match any deployment config file names.

WARNING: See https://github.com/lorenwest/node-config/wiki/Strict-Mode

server started at http://0.0.0.0:7300

#check result, visit http://0.0.0.0:7300

# Stop

#Ctrl+c





