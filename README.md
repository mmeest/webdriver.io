![header](https://capsule-render.vercel.app/api?type=slice&color=auto&height=130&section=header&text=Webdriver.io&fontSize=30&fontAlign=80)

<img src="webdriver.jpg">

# Webdriver.io
Webdriver.io for automated testing

## webdriver.io homepage:
https://webdriver.io/

<img src="node.jpg">

## Node.js JavaScript runtime
https://nodejs.org/

## w3schools on nodejs:
https://www.w3schools.com/nodejs/

* Node.js is an open source server environment.
* Node.js allows you to run JavaScript on the server.

* Node.js is an open source server environment
* Node.js is free
* Node.js runs on various platforms (Windows, Linux, Unix, Mac OS X, etc.)
* Node.js uses JavaScript on the server

* Node.js can generate dynamic page content
* Node.js can create, open, read, write, delete, and close files on the server
* Node.js can collect form data
* Node.js can add, delete, modify data in your database

## Node.js for Windows 7:
Latest version of node.js that works on Win7 is v13.14.0 LTS
https://nodejs.org/download/release/v13.14.0/node-v13.14.0-x64.msi
Tutorial: https://www.centennialsoftwaresolutions.com/post/install-node-js-on-windows-7

To test Node.js version:
```
node -v 
```

## NVM - Node Version Manager
https://github.com/nvm-sh/nvm

To test NPM version:
```
npm -v
```

<img src="npm.jpg">

## NPM - Node.js package manager:
https://www.npmjs.com/

The NPM program is installed on your computer when you install Node.js

## Create new webdriver.io project on command line
**1. Create new project named 'webdriverio-test':**
```
mkdir webdriverio-test && cd webdriverio-test
```
**On ERROR** 'the token '&&' is not a valid statement separator in this version'
Change '&&' to ';':
```
mkdir webdriverio-test ; cd webdriverio-test
```

**2. Initialize project:**
```
npm init -y
```

**3. Install webdriver testrunner:**
```
npm i --save-dev @wdio/cli
```

**4. Generate configuration file 'wdio.conf.js':**
```
npx wdio config -y
```
**On ERROR:** 'The Windows SDK version 8.1 was not found'
Download and run SDK 8.1:
https://developer.microsoft.com/en-us/windows/downloads/sdk-archive/

**On ERROR:** 'error trk0005 failed to locate cl.exe' install global tools:
```
npm install --global --production windows-build-tools
```

** Dependencies installed on package.json: **
* @wdio/gli
* @wdio/local-runner
* @wdio/mocha-framework
* @wdio/spec-reporter
* @wdio/sync
* chromedriver
* wdio-chromedriver-service

**5. Create folder for test files:**
```
mkdir -p ./test/specs
```
**On ERROR:** 'The syntax of the command is incorrect' use backslashes '\':
```
mkdir -p .\test\specs
```

**6. Install 'touch' on node.js:**
```
npm install touch-cli -g
```

**7. Create a new file in that folder (we'll call it basic.js):**
```
touch ./test/specs/basic.js
```

**8. Copy following code to 'basic.js':**
```
describe('webdriver.io page', () => {
    it('should have the right title', () => {
        browser.url('https://webdriver.io')
        expect(browser).toHaveTitle('WebdriverIO · Next-gen browser and mobile automation test framework for Node.js');
    })
}) 
```

**9. Run the test:**
```
npx wdio wdio.conf.js
```

## Sync / Async mode:
https://webdriver.io/docs/sync-vs-async.html

To use async mode @wdio/sync needs to be installed

# Usage

**Link Text**

```
<a href="https://webdriver.io">WebdriverIO</a>
```

To get the anchor element with specific text, query starts with equal sign '=':
```
const link = $('=WebdriverIO')
console.log(link.getText())             // outputs: "WebdriverIO"
console.log(link.getAttribute('href'))  // outputs: "https://webdriver.io"
```
To use partially matching link text '*'
```
const link = $('*=driver')
console.log(link.getText())             // outputs: "WebdriverIO"
```

To use multiple queries
```
const elem = $('header').$('*=driver')
```

**Element with certain text**
```
<h1 alt="welcome-to-my-page">Welcome to my Page</h1>
```

To call current 'h1' element:
```
const header = $('h1=Welcome to my Page')
console.log(header.getText())           // outputs: "Welcome to my Page"
console.log(header.getTagName())        // outputs: "h1"
```

Or use partial text:
```
const header = $('h1=Welcome')
console.log(header.getText())           // outputs: "Welcome to my Page"
```

To get the element by ID:
Example:
```
<i class="someElem" id="elem">WebdriverIO is the best</i>
```
To call it:
```
const classNameAndText = $('.someElem=WebdriverIO is the best')
console.log(classNameAndText.getText()) // outputs: "WebdriverIO is the best"

const idAndText = $('#elem=WebdriverIO is the best')
console.log(idAndText.getText())        // outputs: "WebdriverIO is the best"
```

Tag Name
Example:
```
<my-element>WebdriverIO is the best</my-element>
```
Query:
```
const classNameAndText = $('<my-element />')
console.log(classNameAndText.getText()) // outputs: "WebdriverIO is the best"
```

Name Attribute:
```
<input name="username" value="foobar" />

const classNameAndText = $('[name="username"]')
console.log(classNameAndText.getValue()) // outputs: "foobar"
```
xPath:
```
<html>
    <body>
        <p>foobar</p>
        <p>barfoo</p>
    </body>
</html>
```
To get second paragraph with xPath:
```
const paragraph = $('//body/p[2]')
console.log(paragraph.getText())        // outputs: "barfoo"
```
To use traverse xPath on DOM tree:
```
const parent = paragraph.$('..')
console.log(parent.getTagName())        // outputs: "body"
```
For ID WebDriver has no syntax. To get the element it should use either CSS selector (#<my element ID>) or xPath (//*[@id="my element ID>"])

![footer](https://capsule-render.vercel.app/api?type=slice&color=auto&height=130&section=footer)
