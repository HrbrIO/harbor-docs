# harbor-docs
This is a repository of the Harbor-Docs Mkdocs site.

We are using Mkdocs to build the site.  In addition we are using the mkdocs-material theme with a small modification for harbor colors.

You can add any Markdown files you would like to this site and I will have Mkupdate the site with the new files.

If you'd like to run Mkdocs locally to preview your changes as part of the site you will need to install Mkdocs and the mkdocs-material theme according to this instructions.

## Install Mkdocs
For linux run `sudo apt install mkdocs`.

For Mac run `brew install mkdocs`.

## Clone this Repository

## Install mkdocs-material.

You need to have npm installed on this system.  The base python that comes with your system will work fine.
    
`cd mkdocs-material` 

`npm install`

`pip install -r requirements.txt`

`npm run build`

## Run a Mkdocs preview site locally
Mkdocs allows you to run a local site to preview your changes.  Return to the base `harbor-docs` directory and run

`mkdocs serve`

## Alternative Installation Instructions (from Mitch)

Stock Python may not work due to missing libraries. To fix, do a reinstall via brew:

`brew reinstall python@2`

Supposedly Mkdocs will also work with Python 3, but I haven't tried it.

Once the build is done (a while), install the required packages MANUALLY since the sourcing from the `requirements.txt` may not work (it did not for me):

`pip install mkdocs`  
`pip install Pygments`  
`pip install pymdown-extensions`  
           
Then `cd mkdocs-material`, `npm install`, `npm run build`.

Now `cd ..` and `mkdocs serve`. Voila.



