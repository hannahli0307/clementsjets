# Website for Clements JETS

### General resources to be familiar with
- [Really good javascript docs and tutorials](https://developer.mozilla.org/en-US/docs/Web/JavaScript), keep in mind a lot of the javascript on the site right now is not following best practices and kind of outdated, so when in doubt trust MDN's syntax
- [CSS tutorials and docs](https://developer.mozilla.org/en-US/docs/Web/CSS), CSS can be really fishy sometimes and not intuitive so just ask me or stack overflow if you are having trouble making something look right
- [HTML tutorials and docs](https://developer.mozilla.org/en-US/docs/Web/HTML), it's good to understand how HTML is structured normally before jumping into the .pug files but it should be easy to pick up

### Project Details
| Directory/File Name     | Purpose                       |
| ----------------------- | ----------------------------- |
| index.js                | contains the main server code |
| gulpfile.js             | contains the logic for automatically compiling .scss and .pug files, among other things|
| package.json            | defines what packages we need and their versions |
| package-lock.json       | helps guarantee that the same versions of packages are installed every time, don't touch this one|
| LICENSE/.prettierrc     | ignore for now |
| Procfile                | tells heroku how to start the server |
| favicon.ico             | the icon that appears on browser tab |
| app/                    | contains all the source code that is eventually compiled into HTML/CSS by gulp. These can also be considered "assets" |
| app/js                  | contains javascript that some pages need to be interactive |
| app/scss                | contains .scss files, which lets us write CSS in a more concise and modular way, syntax info [here](https://sass-lang.com/guide)|
| app/templates           | contains .pug files, which lets us write HTML in a more concise and modular way, syntax info [here](https://pugjs.org/language/attributes.html)  |
| dist/                   | contains all the compiled HTML/CSS from app/ directory, you shouldn't have to touch this. This entire folder is generated by gulp. |
| .min.something files    | if you see this, it means this file has been minified, or shrunk down into an unreadable but smaller file, these are generated by gulp. |
| routes/                 | defines the behavior of our server and what it returns when users visit certain URLs (routes) |


### Development Setup
0. Create a file called ```.env``` in the root of your project folder. Copy paste the below content in:
```
    DROPBOX=https://www.dropbox.com/sh/cz2yv2klsv091d3/AACPRZYFUfpraGmWG5UOhJ03a?dl=0
    EVENT_PREP_SHEET=https://docs.google.com/document/d/1yDZ1M3Qo9NWpTo1zSc2EMrBzNgeANkrRYmFZLkexRfM/edit?usp=sharing
    HASH=$2a$08$mQhW0utHaDYytF6ebu3Ie.7UcjejYZIs7hLQAlVGhiG48EIvmaYbu
    TEST_LINK_ARCHIVES=https://drive.google.com/open?id=0BxJxeYCvliIBRklENWxySWhqcUk
```
1. Install build tools
```
    npm i -g gulp
    npm i -g nodemon
```
Gulp is our task runner, nodemon is a tool that restarts the server when server code changes.
2. Open two terminals. In the first one, run this which starts the server:
```
    npm run start:server
```
In the other terminal, run this which starts building assets to HTML/CSS
```
    npm run start:watch-assets
```
3. Go to browser and visit ```localhost:3000```
