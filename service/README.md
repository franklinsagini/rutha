# Rutha Stack - Taming HapiJS and AngularJS #
**Ru** le 
**T** hem 
**H** apiJS 
**A** ngularJS

Pure pragmatic NodeJS stack

### Features ###

After years of dealing with Sinatra (Ruby) and Backbone, and a brief ExpressJS side project, I figure out that:

* **AngularJS** is a faster approach for most use cases where you don't need rocket scientists or rock stars in your roster (team) to learn all the nuances of working with Backbone (e.g. child views).
* Corporate support is a must for open source projects, giving my 2 cents to **HapiJS** because it has all features that you need, is stable, and most important, releases are frequent and contributors are a lot (and they don't jump ship to Golang)
* **Jasmine 2.0 (Server side)**: Both Angular Protractor and Facebook Jest are based on Jasmine. Using Mocha/Chai combo just adds to your learning curve. Jasmine 2.0 has been given more updates than ever before. Is a must have.
* **Grunt JIT**: Is JIT for Grunt. No more waits.
* **BrowserSync**: Choose this because it was painless to configure
* **Underscore for frontend server side templates**: To avoid issues with AngularJS.
* [Grunt ngAnnotate](https://github.com/mzgol/grunt-ng-annotate)
* [Grunt Angular Templates](https://github.com/ericclemmons/grunt-angular-templates)
* [Grunt  Wiredep](https://github.com/stephenplusplus/grunt-wiredep)
* **Rule Them All with a single environment**: Both development and production environment are the same. We concat, annotate, mix some ingredients and offer you the same production environment for development.
* **Specs and Functional Tests (Frontend)**: Based partially on [year of moo](http://www.yearofmoo.com/2013/01/full-spectrum-testing-with-angularjs-and-karma.html) 
* **Frontend** [Todd Motto's](http://toddmotto.com/opinionated-angular-js-styleguide-for-teams/) AngularJS guideline: I also based some ideas on [PackPub's Angular Book](http://www.packtpub.com/angularjs-web-application-development/book?tag=dp/masteringwebwithangularjs-abr1/0913)
* **Visionmedia/debug** [module](https://github.com/visionmedia/debug) by default

### Grunt Help (Service) ###

* `npm start`: Serves API service
* `npm test`: Runs Jasmine NPM specs
* `grunt coverage`: Runs Istanbul code coverage. Outputs HTML reports to `test/coverage/reports`
* `npm run nsp`: Verifies modules that contains security issues
* `grunt migrate:create [--name]`: Creates a migration task. Args: --name: migration name (optional)
* `grunt migrate:up [--revision]`: Migrates up. Args: --revision: revision name (optional)
* `grunt migrate:down [--revision]`: Migrates down. Args: --revision: revision name (optional)



### Nginx routes (Optional) ###

```
server { 
# simple reverse-proxy for Rutha (Very useful!)
    listen       80;
    server_name  localhost;
    access_log   dev.log;
    #error_page   http://here;

  location /api {
    proxy_pass      http://127.0.0.1:3002;
    proxy_redirect  default;
    proxy_set_header Host $host;
  }

  location / {
    proxy_pass      http://127.0.0.1:3005;
    proxy_redirect  default;
    proxy_set_header Host $host;
  }
}

```

### Maintainers, notes ###
Maintain by Rogelio Morrell C. 
Pull Request are welcome but I might not turn around those quickly. 

### Disclaimer ###
Feel free to fork.