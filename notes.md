

======================
Git Branch Management
======================

$ git branch --list
  * master
  version1
  version2
  version3
  version4
  version5
  version6

git checkout <branch>
git branch <new-branch>
git branch -d <branch>

git status
git add -A
git status
git commit -m "."

=================
Heroku Toolbelt
=================

heroku apps
heroku logs --app pnguyen-gumball
heroku pg:psql
heroku pg:psql --app pnguyen-gumball



======================
package.json (changes)
======================

{
  "name": "gumball_v1",
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
  
  