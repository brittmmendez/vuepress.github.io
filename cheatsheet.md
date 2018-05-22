# Cheatsheet: Checklist for creating a VuePress site

## Set up the project directory

* [Create a directory](/creating-the-directories-for-your-vuepress-site.md) for your project.
For example, if your project is at `~/mybook`:

```bash
# Generate full directory path, including the
# necessary hidden directory .vuepress
$ mkdir -p ~/mybook/.vuepress
# These directories hold images and CSS. You 
# don't need to use this convention.
$ mkdir -p ~/mybook/assets/img
$ mkdir -p ~/mybook/assets/css
```

## Create the home page

The home page of a site using the default VuePress theme is kind of a splash screen, more for 
showing off a site than for reference. So give it a nice bold image.

* Change to the project root directory:

```bash
# Replace this with whatever directory
# you used for your VuePress installation.
$ cd  ~/mybook/
```

* Obtain an image file for the main home page image (called the hero image). In this example
it's called logo.png but the name and size don't matter. 

It's best to get one with
a transparent or white background if you're using the default VuePress theme
with no changes.

* Create the file `README.md` and give it the following contents.

```txt
---
# Specify this is the home page 
# (and therefore uses the Home.vue template)
home: true
# Put a big centered H1 in the middle of the page
heroText: Main title of your site

# Image for the center of the home page
heroImage: /assets/img/logo.png

# Explain what the site is all about
tagline: Catchy description of site

# Text for the big green button:
actionText: See our Menu →

# Place big green button should link to. 
actionLink: ./menu.md
---
## Secondary title-less important thatn heroText

And regular text goes here.
```

## Add a title, mobile menu, and search

The site's global title, search capability for header levels 1-3, and mobile
"hamburger" menu are added with `title` and `description` attributes of `config.js`.

* Create the file `/.vuepress/config.js` with contents along these lines:

```javascript
module.exports = {
  title: "Springfiled Dim Sum",
  description: "Springfield's best Chinese food!"
}
```

## Adding other directories

You can add more directories to organize your site. Each directory must contain 
file named `README.md`.