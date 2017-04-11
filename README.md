# Wine Spectator Grand Tour

An Promotional event site, please read below on how to update and generate static content for this project.

# Harpjs Boilerplate

This is a starter-kit for building a static web site dynamically. Perfect for small promotional or event web-sites.
Check Harpjs for advance use like the [M. Shanken](https://github.com/mshanken/mshanken) site.

Harp-Boilerplate works with boostrap 4 by default, move to "less branch" if you want to use less.

Check out [harpjs for more info](http://harpjs.com/docs/).


## Welcome to version 2.

Not much change to it, it jjust now works under docker containers.

## Requirements

You only need docker and [docker](https://www.docker.com/) to run this project. All components are inside so you don'tt need node, grunt, or harp in your local machine. Docker will intall everythin in that container you just have to work in your HTML, CSS, JS.

## How it works

### Start
To start a new project just clone the repo and run the following commands (remove git if you are planing to create as a new repo after you cloned ```rm -R .git``` to clear it first)

1. ```git clone git@github.com:mshanken/harp-boilerplate.git new-repo-name```

	a. cd into the project.

	b. Create a folder in the css folder and name it _vendor ```mkdir _site/public/css/_vendor```

	c. Create a folder in the ja folder and name it vendor ```mkdir _site/public/js/vendor```

	d. Remove git ```rm -R .git```. then add to a new or already initiated repo

	e. _Optional_, create a new branch and start working from it.

2. Run ```docker-compose up -d``` in your teminal start project

That's all. Type this URL ```http://localhost:9000/``` in your browser you have a web site running.<br>
**Note:** There's sass bug running now (not the project though) in Bootstarp4 (which is used in here) so you might not able to see your page the frist time for now just open ```_site/public/css/_vendor/bootstrap.scss``` file and comment out line #51 (e.g // @import "bower_components/bootstrap/scss/carousel";) and them go back to your browser, refresh URL noted or re-open.

Good news, you don't have to refresh, it has browser-sync as well, not running as default but you can just run ```docker-compose exec -d web npm run browsersync``` and now chenge its port to 3000 e.g [http://localhost:9000/](http://localhost:9000/)

### What aboout GH-PAGES?

Once you are ready to deploy just move to gh-pages branch (don't forgte to merge your branch) and run ```docker-compose run web npm run gh-pages``` after that just move your dist (www) folder to your root folder ```mv -r www ./``` now you can commit and push to gh-pages.
## Command lines you can use

```docker-compose up -d``` builds the project in a docker container

```docker-compose exec web npm run browsersync``` starts browser-sync [http://localhost:3000/](http://localhost:3000/) hit ```Ctrl + P and Ctrl + Q``` to detach.

```docker-compose exec web npm run compile``` compiles served site into static HTML in a folder "www"

```docker-compose exec web npm run gh-pages``` drops compiled files into root folder<br>
**Note:** this comand should be used in gh-branch only.

```docker-compose stop``` to turn off the docker container.

```docker-compose down``` to remove this container.

**Note:** It's good practice to always turn container off when not using it.



## Version 1 (this version still in service, just move (checkout) to the sass branch)

## How it works
Before you start, make sure you have the following requirements for using this tool.

1. Ruby
2. Node
3. NPM
4. Harp js ```npm install harp -g```
5. Grunt (you can also run this locally, if prefer)
6. Bower  (you can also run this locally, if prefer)

To start a new project just clone the repo and run the following commands (remove git if you are planing to create as a new repo after you cloned ```rm -R .git``` to clear it first)

1. ```git clone git@github.com:mshanken/harp-boilerplate.git new-repo-name```

	a. Remove git if you want to add this tool into a new or already initiated repo ```rm -R .git```

	b. _Optional_, create a new branch and start working from it.
	
	c. <del>For a in progress project using this tool create a new branch and copy all its content in the root folder, commit and push the new branch, them move to your working branch and merge the new branch.</del>

2. ```npm install```<br>
**Note:** Because harp-js uses Ruby for sass and other features under the hood, you might see error logs in your screen, if that's the case, just run this ```npm install grunt-harp``` with sudo before the next command)
3. ```bower install```
4. ```mkdir _site/public/js/vendor```
5. ```npm start```<br>
**Note:** This command should run only once for every new project to bring all main components up.
6. ```grunt server```

Check [http://localhost:9000](http://localhost:9000) in your browser. That's all, start working in your project now.

If you want to run with browser-sync just type the following ```browser-sync start --proxy 'localhost:9000' --files '_site/public/**/*.jade, _site/public/**/*.md, _site/public/**/*.scss, _site/public/**/_data.json'``` (this will require you to open a new tap in your terminal as main server need to run at the same time ```grunt server```)

## list of commads
This is a list of commads at your dispose to create a simple static web-site. Enjoy it!

### ```grunt server```
Runs harp server from your harpjs working directory ```_site/```, after you run this command open your browser with this location http://localhost:9000 to preview it. Type ```ctrl+c``` to turn off the server.

### ```grunt compile```
Runs harp compile to generate the static HTML of your dinamic website.

### ```grunt static```
Like ```grunt server``` it runs another server but this one serves the generated HTML (compiled), this can help to review the generated HTML site. Open your browser with this url http://localhost:8800.

### ```grunt gh-pages```
This command will copy the generated HTML (compiled) version of your site at rooted level so it can be render at github gh-pages.

**NOTE:** this command should run once you are in the **_gh-pages_** branch only.

## What's in here?
Once you have followed the initial steps check your new working directory _site/public folder to familiarize, everyhing you need to create a website is there, you can add more assets trough npm or bower if needs to.

Bootstrap 4.<br>
jqury latest (3^).<br>
HarpJS built-in preprocessing configured to work with a default theme.<br>
Web-server to preview your work on your browser.<br>
BrowserSync to preview your changes as you work with out refreshing your browser.<br>
gh-pages branch to compile your work into the root folder for github to render your static html.<br>
Google analitics and openGraph code ready to use, turned off by default.

## Projects using this tool:
1. [M. Shanken](https://github.com/mshanken/mshanken)
2. [WS Apps site](https://github.com/mshanken/appswinespectator)
3. [Wine Experience](https://github.com/mshanken/wineexperience)

Others should follow, specially for 2 or more static page web sites.

