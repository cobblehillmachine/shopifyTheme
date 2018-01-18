# Cobble Chill Shopify Theme

This is the base theme all Cobble Hill Shopify sites will use here on out.

## Getting Started

These instructions will get you a copy of the theme up and running on your local machine for development and testing purposes. For first time installation be sure to read PREREQUISITES first, to insure the theme will download correctly. See DEPLOYMENT for notes on how to deploy the project on a live system.

### Prerequisites

For first time installation you will need to make sure you have NPM and GULP installed on your system. After that we will need to install the Slate CLI tools to do this run the following code anywhere in your terminal:

```
npm install -g @shopify/slate
```

### Installing

These step by step examples will tell you how to get a new Theme environment running.

First clone the git repo in your desired location

```
git clone https://github.com/Vicula/shopifyTheme.git .
```

Remove connection to current git repository

```
git remote remove origin
```

Connect to new Cobble Hill repository

```
git remote add origin [repo url]
```

Find the config.yml file one folder down and open it.
Replace the store field under the Development enviroment with your current shopify site like so:

```
store: myfairygardensshop.myshopify.com
```

After adding the store url you will want to go to your theme location in your terminal and extract the theme like so:

```
slate deploy -m
```

This will open the file location of the ziped file and also open your shopify admin.
You will need to locate the Upload Theme button to the left of the current themes.
Once the Theme is uploaded you will want to click the customize button.
Once in the editor look at your browser url:

```
/admin/themes/196052232/editor
```

You will want to grab the number from the url and copy to your clipboard.
Go back to your config.yml file and replace the theme id with the number you just grabbed:


```
theme_id: "196052232"
```

Now we will need to go back to the shopify admin and click on the Apps section.
Once here scroll to the bottom and click the 'Mange Private Apps' button.
Once in here find the create new private app button.
Give yourself Read and write access to the Theme templates and theme assets option.
Once created grab the app Password and copy to your clipboard.
Replace the password section in the config.yml with this password.

```
password: 1234567890123456789012345667
```

After all of this you are ready to launch your theme watchers and deploy scripts!

For first time setup run the start command in your terminal inside your theme directory:

```
slate start
```
This should be for first time use only or to complelely overwrite the theme that is currently sitting on their shopify site

This is going to open a local version for you to work on localy and without internet you will have access to browsersync for debug and other development needs.

To kill any command running press this command in your terminal

```
cntrl + c
```


## Commands

### Here is a list of general commands:

### Slate

Get help with Slate command

```
slate [command] -h
```

Get slate version

```
slate -v
```

Run slate's built in Lint package

```
slate test
```

Get a zip file of your theme

```
slate zip
```

Run slate's watchers

```
slate watch
```
```
slate watch -e,   deploy to a specific environment
slate watch -n,   disable Browsersync
```

### Theme Kit

Opens the preview page for the selected enviroment

```
theme open --env=development
```

Upload select files to specified enviroment

```
theme upload -d src -e development templates/404.liquid
```

## Deployment

To deploy the theme to the live site run the deploy command in your theme directory. This will overwrite all the theme code on the shopify theme currently. This also deploys to all the enviroments in your config.yml file.

```
slate deploy
```

If you want to deploy only to a specific enviroment you can use the `-e` flag to dictate one.

```
slate deploy -e development
```

And if you want to be picky and choose multiple:

```
slate deploy -e development,staging,production
```

If you are concerned about overwriting anything in the theme you can download the theme from shopify, which will overwrite all the local theme code on your computer. The `-d` flag is for the directory to install to so we want `src` and the `-e` flag is for the enviroment from your config.yml so we `development`.

```
theme download -d src -e development
```

To download specif assets list the file path after the enviroment:

```
theme download -d src -e development templates/404.liquid
```

And to download multiple assets just space seperate the file paths:

```
theme download -d src -e development templates/404.liquid templates/article.liquid
```

If you get an error from Theme Kit try to reinstall it with this command:

```
curl -s https://raw.githubusercontent.com/Shopify/themekit/master/scripts/install | sudo python
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Authors

* **Victor Carpenter** - *Initial work* - [Vicula](https://github.com/Vicula)

<!-- ## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags).

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc -->
