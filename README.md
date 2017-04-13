# Wine Spectator Grand Tour

An Promotional event site, please read below on how to update and generate static content for this project.

# Harpjs Boilerplate

1. git clone git@github.com:mshanken/wsgtwebAd.git

2. cd into the project.

3. Create a folder in the css folder and name it _vendor ```mkdir _site/public/css/_vendor```

4. Create a folder in the ja folder and name it vendor ```mkdir _site/public/js/vendor```


## Avialable commands.

```docker-compose up -d``` builds the project in a docker container.

```docker-compose exec web npm run browsersync``` starts browser-sync [http://localhost:3000/](http://localhost:3000/) hit ```Ctrl + P and Ctrl + Q``` to detach.

```docker-compose exec web npm run compile``` compiles served site into static HTML in a folder "www"

```docker-compose exec web npm run gh-pages```  what this command does is compiled (if not compiled) then drops compiled files into root folder<br>
**Note:** this comand should be used in gh-pages branch only.

Run ```docker-compose exec web /bin/bash``` to access docker machine from terminal an run other grunt/npm comands.

```docker-compose stop``` to turn off the docker container.

```docker-compose down``` to remove this container, Always use this command after you are done with this repo.

Read more in [here](https://github.com/mshanken/harp-boilerplate)