
======================
package.json (changes)
======================

{
  "name": "gumball",
  "description": "Simple Test Form",
  "version": "1.0.0",
  "main": "app.js",
  "engines": {
    "node": "4.1.1"
  },
  "private": true,
  "scripts": {
    "start": "node app.js",
    "test": "vows --spec"
  },  
  "dependencies": {
    "express" : "3.x",
    "fs" : "0.0.2",
    "node-rest-client" : "1.4.1",
    "mongodb" : ">=2.0.14",
    "vows" : "*"
  }
}

=================
app.js (changes)
=================

app.set('port', (process.env.PORT || 5000));

app.post("*", handle_post );
app.get( "*", handle_get ) ;

app.listen(app.get('port'), function() {
  console.log('Node app is running on port', app.get('port'));
});


===========
.travis.yml
===========

language: node_js
node_js:
  - "4.1"
  

======================
MongoDB / MongoLabs
======================

  https://devcenter.heroku.com/articles/mongolab
  http://docs.mongolab.com/connecting/

  heroku config --app pnguyen-gumball | grep MONGOLAB_URI
  MONGOLAB_URI: 
  mongodb://heroku_jc07tp0r:paf27qhrk1l9v9bj2ecqks4n5c@ds045614.mongolab.com:45614/heroku_jc07tp0r

  var db_host = "ds045614.mongolab.com" ;
  var db_port = "45614" ;
  var db_user = "heroku_jc07tp0r" ;
  var db_pwd  = "paf27qhrk1l9v9bj2ecqks4n5c" ;
  var db_name = "heroku_jc07tp0r" ;

  To connect using the mongo shell:

	  mongo ds045614.mongolab.com:45614/heroku_jc07tp0r -u heroku_jc07tp0r -p paf27qhrk1l9v9bj2ecqks4n5c

  To connect using a driver via the standard MongoDB URI (what's this?):

	  mongodb://heroku_jc07tp0r:paf27qhrk1l9v9bj2ecqks4n5c@ds045614.mongolab.com:45614/heroku_jc07tp0r
 	
  Troubleshoot Connections:

    ping ds045614.mongolab.com
    nc -w 3 -v ds045614.mongolab.com 45614
    heroku logs --app pnguyen-gumball
    
  MongoDB Node Drivers:
  
    https://docs.mongodb.org/ecosystem/drivers/node-js/
  