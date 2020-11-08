![header](https://capsule-render.vercel.app/api?type=slice&color=auto&height=130&section=header&text=Webdriver.io&fontSize=30&fontAlign=80)

<img src="webdriver.jpg">

# Webdriver.io
Webdriver.io for automated testing

## webdriver.io homepage:
https://webdriver.io/

WebdriverIO needs Node.js installed

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

**Dependencies installed on package.json:**
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

To use sync mode @wdio/sync needs to be installed

## Cross browser usage:
https://webdriver.io/docs/driverbinaries.html

Windows (64 bit / Chocolatey) install: \
choco install selenium-gecko-driver

<img src="selenium.jpg">

## Selenium Standalone Service:
https://webdriver.io/docs/selenium-standalone-service.html
https://www.npmjs.com/package/selenium-standalone

Supported Webdrivers:
* ChromeDriver
* FirefoxDriver
* IEDriver
* Edge WebDriver
* Chromium Edge WebDriver

To install Selenium Standalone Service globally:
```
npm install selenium-standalone@latest -g
selenium-standalone install && selenium-standalone start
```

To install Selenium Standalone Service local package:
```
npm install selenium-standalone --save-dev
./node_modules/.bin/selenium-standalone install && ./node_modules/.bin/selenium-standalone start
```

**Configuration**

By default, Google Chrome and Firefox are available when installed on the host system. In order to use the service you need to add selenium-standalone to your service array:
```
// wdio.conf.js
const drivers = {
    chrome: { version: '86.0.4240.22' }, // https://chromedriver.chromium.org/
    firefox: { version: '0.27.0' } // https://github.com/mozilla/geckodriver/releases
    chromiumedge: { version: '85.0.564.70' } // https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/
}

export.config = {
    // ...
    services: [
        ['selenium-standalone', {
            logPath: 'logs',
            installArgs: { drivers },
            args: { drivers },
        }]
    ],
    // ...
};
```

## Powershell for installing Chocolately:
https://github.com/PowerShell/PowerShell/releases/tag/v7.0.3
https://www.thomasmaurer.ch/2019/07/how-to-install-and-update-powershell-7/
https://www.thomasmaurer.ch/2020/03/whats-new-in-powershell-7-check-it-out/

<img src="choco.jpg">

## Chocolatey Package manager on Windows for Firefox Gecko driver:
https://chocolatey.org/

A. To install on Windows Powershell:\

B. To download directly Nupkg(.zip file):\
https://chocolatey.org/api/v2/package/chocolatey
In Visual Studio Code: Tools > Options > NuGet Package Manager > Package Sources

<img src="allure.jpg">

## Allure Reporter
https://webdriver.io/docs/allure-reporter.html
https://docs.qameta.io/allure/

* Installation
```
npm install @wdio/allure-reporter --save-dev
```

Configure the output directory in your wdio.conf.js file:
```
exports.config = {
    // ...
    reporters: [['allure', {
        outputDir: 'allure-results',
        disableWebdriverStepsReporting: true,
        disableWebdriverScreenshotsReporting: true,
    }]],
    // ...
}
```

**Allure command-line Tool:**
https://www.npmjs.com/package/allure-commandline
* requires Java 8 or higher
https://www.oracle.com/java/technologies/javase-jre8-downloads.html

To install Allure command-line tool:
```
npm install -g allure-commandline --save-dev
```

To generate reports with Allure for example('allure-results' folder):
```
allure generate allure-results/ && allure open
```

<img src="chai.jpg">

## Chai JS for extra features
Chai is free and open source library to use on javascript testing framework.\
https://www.chaijs.com/

# WebdriverIO Usage

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
To use partially matching **link text** '*'
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

To get the element by **ID**:
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

**Tag Name**
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
**xPath:**
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
For **ID** WebDriver has no syntax. To get the element it should use either CSS selector (#<my element ID>) or xPath (//*[@id="my element ID>"])

```
const elem = $('#elem') // or $(() => document.getElementById('elem'))
elem.$(function () { return this.nextSibling.nextSibling }) // (first sibling is #text with value ("↵"))
```

<img src="vscode.jpg">

# Autocomplete in Visual Studio Code:

<img src="mocha.jpg">

**Mocha Snippet**
Describe block -> desc + 'Enter'

# Actions:
**Open page**
```
browser.url('https://www.ebay.com');
```

**$ - Find Element**\
https://webdriver.io/docs/api/browser/$.html

**$$ - Find Multiple Elements**\
https://webdriver.io/docs/api/browser/$$.html
$$ - returns an Array. To get FIRST element from array:
```
return $$('section.b-promobanner')[1];
```

**Value to variable(by ID)**
```
const searchBtn = $('#gh-btn');
```

**Nth selection from dropdown**
```
const category = $('#gh-cat option:nth-child(1)');
```

**Element with DOM element name and class name**
```
const poromoBanner = $('section.b-promobanner');
```

**Insert value to textField**
```
searchInput.addValue('My text');
```

**Click a button**
```
searchBtn.click();
```

**EXPECT**\
https://webdriver.io/docs/api/expect-webdriverio.html

**Expect browser title**
```
expect(browser).title('Electronics');
```

**Expect to have url**
```
browser.url('https://webdriver.io/')
expect(browser).toHaveUrl('https://webdriver.io')
```

**Expect textInputField to have value**
```
expect('searchInput').toHaveValue('My Text');
```

**Expect element displayed**
```
const elem = $('#elem')
expect(elem).toBeDisabled()
// same as
expect(elem).not.toBeEnabled()
```

**Expect to have text containing**
```
browser.url('https://webdriver.io/')
const elem = $('.tagline')
expect(elem).toHaveTextContaining('browser and mobile automation test framework')
```

**Expect to have link containing**
```
const link = $('a')
expect(link).toHaveLinkContaining('webdriver.io')
```

**Expect to be clickable**
```
const elem = $('#elem')
expect(elem).toBeClickable()
```

**Code Reuse - Page Object Model**
https://webdriver.io/docs/pageobjects.html

#WebdriverIO tutorial from Automation Bro on YouTube
https://www.youtube.com/watch?v=e8goAKb6CC0&list=PL6AdzyjjD5HBbt9amjf3wIVMaobb28ZYN

![footer](https://capsule-render.vercel.app/api?type=slice&color=auto&height=130&section=footer)
