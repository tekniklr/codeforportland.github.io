# Code for Portland

[![Build Status](https://travis-ci.org/CodeForPortland/codeforportland.github.io.svg?branch=master)](https://travis-ci.org/CodeForPortland/codeforportland.github.io)

Repo for the homepage of Code for Portland, a Code for America brigade based in Portland, Oregon.

- [projects](projects) (work in progress)

## Make Edits in your Browser

Adding pages and posts is easy!  Just fork the repository and add and edit away.  New to Jekyll?  [Read up on creating post files](http://jekyllrb.com/docs/posts/#creating-post-files) and [check out an existing post](/news/_posts/2014-06-03-ndoch-wrap-up.md) to find the correct front-matter variables.

## Previewing Website Changes Locally

If you plan on just writing blog posts or create pages without editing any JS or CSS assets, you can preview the site locally with a working copy of Ruby and Bundler. Follow this guide to get Jekyll running locally: [help.github.com/articles/using-jekyll-with-pages](https://help.github.com/articles/using-jekyll-with-pages#installing-jekyll)

Once you have that working you can preview the website by running the following command in the website directory:

```cli
~ $ jekyll serve --watch
# => Now browse to http://localhost:4000
```

## Full Development Environment

The site's CSS and JS is compiled and minified using SASS and Grunt.  If you want to edit these asses you must set up a full Node.js + Ruby + Grunt + Sass + Jekll development environment.

### Build Prerequisites

- [Git](http://git-scm.com/)
- [NodeJS](http://nodejs.org) (v0.10.26+ and NPM v1.4.4+)
  - [Bower](http://bower.io/) with `npm install -g bower` (v1.3.2+)
  - [Grunt](http://gruntjs.com) with `npm install -g grunt-cli`
- [Ruby](https://www.ruby-lang.org/en/) (Follow this [Guide](https://help.github.com/articles/using-jekyll-with-pages))
  - [Bundler](http://bundler.io) with `gem install bundler`
    - [Jekyll](http://jekyllrb.com) with `bundle install` in the working directory

### Building the Site

> **Warning:** The site's build scripts will overwrite anything in the `_dev` or `_site` directories, without any warning whatsoever. Similarly, the `assets/js` and `assets/css` directories should be considered forfeit as well: the SCSS and JS compilation scripts overwrite stuff in there!

Before you get started, get your prerequisites installed:

```cli
# With a working npm install
npm install -g grunt-cli
npm install -g bower

# With a working gem install
gem install bundler

cd <project_directory>
npm install
bower install
bundle install
```

There are two build targets: `dev`, and `deploy`.

#### Running the Development Server

The provided Gruntfile gives you a local copy of the site, running on `http://localhost:8002`. Run 

```
grunt dev
``` 

to build the dev site, and serve it on that address. Changes made to any relevant files will trigger a rebuild and livereload in any browsers you have open to the site.

#### Building the Production Site

The production site is build by issuing a `grunt deploy`. Then, commit your changes to the `gh-pages` branch, or your `master` branch if this is your github.io page.

> **Note:** Although Github's Jekyll will be building your site, you still need to run the `grunt deploy` script to generate minimized assets for your site!

## Specifications

- Photos for the main page should be 3840 × 1200 for Retina displays, and 1920 × 600

## License

[MIT](LICENSE)
