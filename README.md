# How to import a package published on Github Packages Registry

For example, we have a package name `sample-npm-package` at `https://github.com/trbhoang/sample-npm-package`

To install this package to your nodejs project:
1. Add to `.npmrc` file in your root project directory

    ```
    @[USERNAME/ORGANIZATION]:registry=https://npm.pkg.github.com
    ````

2. Generate a Github personal access token (TOKEN) and add below line to your root `~/.npmrc` file (at home directory)

    ```
    //npm.pkg.github.com/:_authToken=[TOKEN]
    ```
    or `npm login` using your Github username and token

    ```
    $ npm login --scope=@OWNER --registry=https://npm.pkg.github.com
    > Username: USERNAME
    > Password: TOKEN
    > Email: PUBLIC-EMAIL-ADDRESS
    ```

3. Install package

    From the command line:
    ```
    $ npm install @[USERNAME/ORGANIZATION]/sample-npm-package@1.0.0
    ```
    Via package.json:
    ```
    "@[USERNAME/ORGANIZATION]/sample-npm-package": "1.0.0"
    ```


## Generate Github personal access token

Goto: Github > Settings > Developer settings > Personal access tokens

Generate new token and grant at least `read:packages` permission.