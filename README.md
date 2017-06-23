OpenShift Logos Icon Font
===========================

To view a list of all the glyphs in the font along with their codes/ligatures visit:

<https://rawgit.com/openshift/openshift-logos-icon/master/demo.html>

## Contributing

### Getting Started

Development dependencies are managed using NPM; therefore, [NPM](https://docs.npmjs.com/getting-started/installing-node) is required.

```
npm install
```

### Modifying Font Files

The font files are generated using [IcoMoon](http://icomoon.io/app).

Go to [Manage Projects](https://icomoon.io/app/#/projects)

![image](https://cloud.githubusercontent.com/assets/12733153/15152985/71b8c62a-16a5-11e6-9d3c-d01be57f3c54.png)

Import the project [`selection.json`](selection.json) and Load it:

![image](https://cloud.githubusercontent.com/assets/12733153/15152997/83795582-16a5-11e6-9b64-370884453684.png)

To add new icons to the set, click on the right-hand kabob menu and select “Import To Set”.

![image](https://cloud.githubusercontent.com/assets/12733153/15153017/9411521e-16a5-11e6-9a70-e37e73c16734.png)

Ensure the new icons you added are selected.

Generate the font files by clicking on the “Generate Font” button at the bottom of the page:

![image](https://cloud.githubusercontent.com/assets/12733153/15153037/a676306e-16a5-11e6-8759-03845f0793c3.png)

In that same location, click on the “Download” button.  This will download a zip file. Expand the zip file and copy the following (overwriting your existing files):

* demo-files
* demo.html
* fonts
* selection.json

Update `less/variables.less` and `less/openshift-logos-icon.less` with your new icons.

Run a [build](#building).

### Building

Builds are done via Grunt.

```
grunt
```

### Releasing

To release a new version version, edit `bower.json` and `package.json` accordingly.

Update the version listed in `bower.json` by editing the file and changing the line:

```
"version": "<new_version>"
```

Update the version listed in `package.json` by editing the file and changing the line:

```
"version": "<new_version>"
```

Commit the version bump:

```
git commit -a -m "Version bump to <new_version>"
```

Tag and push upstream (assuming you have commit access):

```
git tag <new_version>
git push && git push --tags
```

The Bower package manager determines available versions and installs based upon git tags, so the new version will now be automatically available via Bower.

To publish a new version to npm, execute:

```
npm publish
```
