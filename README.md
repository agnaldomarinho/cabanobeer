Site da HE:labs
==============

http://helabs.com.br


## Maintainers

- [Thiago Gonzalez](https://github.com/thiagonzalez)
- [Mikael Carrara](https://github.com/mikaelcarrara)

## Running Server

Running foreman will start the jekyll server, will compile your sass files and compile your javascripts.

```sh
$ foreman start
```

## Push to staging

If you want to test and browse website before you push it to public, use staging.

```sh
$ rake staging
```

Staging version of the website is available at staging.helabs.com.br.

## Compiling SASS

When using Foreman to run the server it will also start a Guard process that will watch for changes on the files in the `sass` folder and compile them. No need to run `compass watch` or Grunt.

## Problem with SASS+Git

The Git have a problem with SASS. So when you have a conflict in the generated file by SASS+Compass (stylesheets/style.css), please do not fix this conflict, just delete this conflicted file and generate a new. So you can run this:

```sh
$ git add stylesheets/style.css
$ git rebase --continue
```

## Editing CSS

You can edit the SCSS files in the sass folder.
In the stylesheets folder we have just the generated files by Grunt/Compass.

## Adding A Project To Your Profile

* Check if the project exists inside ```_data/mvp.yml```. If it's there jump to the last step.
* Put a screenshot of the project with 800x465 size and .jpg extension into the ```images/projects/``` folder.
* Create a new entry in ```_data/mvp.yml``` with the following format:

```yaml
  -
    name: project name
    url: external url for the project
    slug: an identifier for the project
    image: /images/projects/my_project.jpg
    description: Describe what the project does
    highlighted: true # if it's highlighted in the http://helabs.com.br/en/work/ page
```

* Open your profile page file. It's inside ```_posts/time```. Add the project slug under ```projects``` property.

## Import blogposts

```sh
$ rake import:blogposts
```

## Remove unused images

```sh
$ rake prune_images
```

**Use this carefully!!!**

## Creating your profile

Run `rake new_profile` task to generate some basic structure for the "blog post"
associated with your profile.

## Made with love by HE:labs

![HE:labs](http://helabs.com.br/images/logo.png)

This app was created and is maintained by [HE:labs](https://github.com/Helabs).
