# Create and publish a Nuxt.js powered website on Github pages
#### 1.  To get started quickly you can use the create-nuxt-content-docs package.
    `yarn create nuxt-content-docs <project-name>`
#### 2.	cd my-project
#### 3.	Install vue-cli:
    `npm install -g vue-cli`
    `npm install`
#### 4.	Update nuxt.config.js to add a base URL (replace my-project by your project name):
    `router: { base: '/my-project/' }`
    
```js
    
    import theme from '@nuxt/content-theme-docs'

    export default theme({
     docs: {
       primaryColor: '#E24F55'
    },
    router: { base: '/<my-project>/' }
  })
```
    
#### 5.	Install push-dir:
    `npm install push-dir --save-dev`
#### 6.	Create a deploy command to publish to Github pages by editing package.json file and adding this line at the beginning of the script section:
    `"deploy": "push-dir --dir=dist --branch=gh-pages --cleanup",`
    
For example

```
{
  "name": "installation-nutx",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "nuxt",
    "build": "nuxt build",
    "start": "nuxt start",
    "generate": "nuxt generate",
    "deploy": "npm run build && gh-pages -d dist --repo https://github.com/standards-hub/<my-project>.git"
  },
  "dependencies": {
    "@nuxt/content-theme-docs": "^0.10.1",
    "nuxt": "^2.15.2"
  },
  "devDependencies": {
    "push-dir": "^0.4.1"
  }
}
```

#### 7.	Then commit and push your code to your repository (replace me by your name and my-project by your project name):
      `git init
      `git add .
      `git commit -m "init"
      `git remote add origin https://github.com/userAccount/my-project.git
      
      Then, create "gh-pages" in the GitHub repository, then run the command:
      
      `git push -u origin master`
      
 
#### 8.	Generate the site and publish it:
    `npm run generate`
    `npm run deploy`
