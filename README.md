Based on
[SO20459367](http://stackoverflow.com/questions/20459367/redirect-bots-using-heroku-to-a-different-server),
this is the model for how to port a dotCloud app to cloudControl with
minimal changes.

##Step 1 Create a custom app
`cctrlapp myapp create custom --buildpack https://github.com/metalivedev/heroku-buildpack-multi`

##Step 2 Add Nginx and Python to `.buidpacks`

    echo 'https://github.com/metalivedev/nginx-buildpack.git' >> .buildpacks
    echo 'https://github.com/metalivedev/buildpack-python.git' >> .buildpacks
    git commit .buildpacks -m'Add buildpack-multi config'

##Step 3
