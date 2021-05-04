# Q4 Blank Template

Project Blank

## Software Requirements
- [Visual Studio Code](https://code.visualstudio.com/) (recommended)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Node.js](http://nodejs.org/)
- [npm](http://npmjs.org/)

## Caution
Please don't edit files in the `dist` subdirectory as they are generated via Grunt. You'll find source code in the `src` subdirectory!

## Software Requirements
- [Visual Studio Code](https://code.visualstudio.com/) (recommended)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Node.js](http://nodejs.org/)
- [npm](http://npmjs.org/)

## Starting builder
First, ensure that you have the latest [Node.js](http://nodejs.org/) and [npm](http://npmjs.org/) installed.

1. Clone the repo and branch off. Branch name convention project-{client-q4web-hostname}.
2. Run `npm install` to install all dependencies
3. Copy desired template folder (should be the same template that the CMS is cloned from). Can be found in `css/`
4. Paste folder and contents in `builder/projects`. Rename folder to client's web hostname. This is now your working directory.
5. Run `npm run watch-css`

## Styling in the CMS
This step requires a local server for your compiled client and master css to be added under Site List. Recommended tool is [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).

e.g. Local CSS Urls
`http://127.0.0.1:4690/test/master/global_master.css`
`http://127.0.0.1:4690/test/master/client_master.css`

1. Deactivate global and client css under CSS List
2. Add local urls in Site List > Site Link Tags

## Tips and Troubleshooting

- CSS updates aren't showing up. Check for errors in the terminal could be sass is failing to compile
- When creating new sass files, make sure it is added in the master imports
- Images used for background styling will need to be saved locally as well as uploaded in the CMS
- `CTRL + SHIFT + F` will help you find the sections of content faster


--------------------------------------------------------------------------------------------------

# Maintaining source code and templates

## Modifying the code
First, ensure that you have the latest [Node.js](http://nodejs.org/) and [npm](http://npmjs.org/) installed.

Test that Grunt's CLI is installed by running `grunt --version`.  If the command isn't found, run `npm install -g grunt-cli`.  For more information about installing Grunt, see the [getting started guide](http://gruntjs.com/getting-started).

1. Fork and clone the repo.
2. Run `npm install` to install all dependencies (including Grunt).
3. Run `grunt` to grunt this project.

Assuming that you don't see any red, you're ready to go. Just be sure to run `grunt` after making any changes, to ensure that nothing is broken.

## Documentation
SassDoc & JSDoc are located in the `docs` directory. Run `grunt` to update docs.

## Additional

If you want to setup your environment to work from blank, and already run apache follow the setups below to add a virtual host

For Window users using Apache 2.4+

	1. Stop Apache
	2. Open notepad.exe as admin
	3. Open C:\xampp\apache\conf\extra\httpd-vhost.conf
	4. Paste the below to the bottom of the file replacing `D:/q4-blank_template/` with the correct path to the repo

		NameVirtualHost *:80
		<VirtualHost *:80>
			DocumentRoot "D:"
			ServerName localhost
		</VirtualHost>

		<VirtualHost *:80>
			DocumentRoot "D:/q4-blank_template/dist"
			ServerName blank.dev
			ServerAlias www.blank.dev
			<Directory "D:/q4-blank_template/dist">
				AllowOverride All
				Require all Granted
			</Directory>
		</VirtualHost>

	5. Save
	6. Open C:/Windows/System32/drivers/etc/hosts
	7. Paste to the bottom of your host file

		127.0.0.1             localhost
		127.0.0.1             blank.dev
		127.0.0.1             www.blank.dev

	8. Save
	9. Restart Apache

For OSX users using Apache 2.4+

	1. Using finder, navigate to the apache configuration files (/etc/apache2/extra/httpd-vhost.conf)
	2. Replace or add the below to the bottom of the file replacing `/Volumes/Drive/q4-blank_template` with the correct path to the repo

		<VirtualHost *:80>
			DocumentRoot "/Volumes/VITALIZ Q4/Q4 FED"
			ServerName localhost
		</VirtualHost>
		<VirtualHost *:80>
			DocumentRoot "/Volumes/Drive/q4-blank_template/dist"
			ServerName blank.dev
			ServerAlias www.blank.dev
			<Directory "/Volumes/Drive/q4-blank_template"/dist>
				AllowOverride All
				Require all Granted
			</Directory>
		</VirtualHost>

	3. Save (you will be asked for your password for overwrite permissions)
	4. Using finder, navigate to your host file (/etc/hosts)
	5. Make sure the following lines are in your host file

		127.0.0.1             localhost
		127.0.0.1             blank.dev
		127.0.0.1             www.blank.dev

	6. Save
	7. Restart Apache