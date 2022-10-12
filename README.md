# VueJS Site Template
Vue 3.0

### Setup node version
Currently, node version 14.17.0 works best with our viewbooks.
The .nvmrc file defines this as the version we are using.
To use this, run:
```
nvm use
```

### Install dependencies
First, install Yarn dependencies:
```
yarn
```

### Start the local server
The following command creates and runs a temporary server to view the site locally.
```
yarn dev
```
The command will output the server URL to visit in your browser, ex. http://localhost:3000.

### Test the build locally
The following command creates the build.
```
yarn build
```

The following command creates and runs a temporary python server to view the site in `dist` locally.
```
cd dist
```
```
python3 -m  http.server 8000 
```
The command will output the server URL to visit in your browser, ex. http://localhost:8000.

### Specifying the base URL
1. Determine the base path of your site. If the site lives in a subdirectory (e.g. uiowa.github.io/vuejs-site-template), then the base path of the site will be `/vuejs-site-template`. If the application isn’t served from a subdirectory, then the base path is `/`
2. In the following line change `—base=/vuejs-site-template/` to `—base-=BASE_PATH/` where BASE_PATH is replaced with the path you determined in the previous step:  
https://github.com/uiowa/vuejs-site-template/blob/ad37ed9dc98658383ab26a4bd02dcdec1a518c97/.github/workflows/gh-pages.yml#L75  
3. In the following line change `—base=/vuejs-site-template/latest/` to `—base-=BASE_PATH/latest/` where BASE_PATH is replaced with the path you determined in the previous step:  
https://github.com/uiowa/vuejs-site-template/blob/ad37ed9dc98658383ab26a4bd02dcdec1a518c97/.github/workflows/gh-pages.yml#L84 

### Creating a PR
1. Once your feature branch has been created, you will need to run the following command: `git push origin feature_branch`.
2. This will generate a url to use, ex. https://github.com/uiowa/vuejs-site-template/pull/new/feature_branch. 
3. Set the upstream branch with `git push --set-upstream origin feature_branch`.
4. Once you open the url, make sure that you switch the base to `develop` instead of `main` and create the pull request. 
5. When the pull request is approved, merge into `develop`.

### Common errors
If the commands listed above for local development are not working, delete your `node_modules` folder and run `yarn install`. 