# Red Hat OpenShift Data Science Quick Course

Welcome to the OpenShift Data Science quick course!. This course uses standard asciidoc for content authoring that is then rendered to HTML and hosted by GitHub Pages. It uses the Antora publishing platform (https://antora.org) to transform the asciidoc conent to HTML.

To contribute, you can use locally installed tooling on your workstation, or you can use OpenShift DevSpaces to work with content using a web based IDE without the need to install anything.

## Locally installed Tooling

1. Install an LTS version of the Node.js runtime on your workstation.
2. Clone this Git repository to a folder of your choice. For the following steps in this README, this folder is indicated by *$CONTENT_ROOT*.
3. Install an editor of your choice. We recommend Visual Studio Code with the *asciidoctor* plug-in.
4. Follow the steps in the *Previewing HTML content and publishing* section.

## The "Easy Button" aka OpenShift DevSpaces

1. To open and edit the asciidoc files in OpenShift DevSpaces, click on the **Developer Workspace** badge below and log in using your provided OpenShift credentials:

[![Contribute](https://www.eclipse.org/che/contribute.svg)](https://devspaces.apps.cluster-z56gz.z56gz.sandbox2456.opentlc.com/#https://github.com/rsriniva/rhods-quick-course)

1. If you are using DevSpaces for the first time, select the **httpasswd** option and log in using the username and password provided to you for DevSpaces. When prompted, allow all permissions. You should see your workspace starting to load.

2. If you launch the DevSpaces workspace for the first time, it will take a few minutes to download the container image, clone the Git repository, and set up your project. All the required tooling and IDE plugins are automatically installed and set up for you.

3. Follow the steps in the *Previewing HTML content and publishing* section.

## Previewing HTML content and publishing

1. All commands in the following steps are to be run from the *$CONTENT_ROOT* folder. Navigate to this folder from the VSCode terminal (Press **Ctrl + `**):

```bash
$ cd $CONTENT_ROOT
```

2. Run **npm install** to install the Node.js dependencies for the project.

```bash
$ npm install
```

3. The Git repository contains the default chapter and section stubs with comments from the product owner/architect to help guide you. Inspect the *$CONTENT_ROOT/antora.yml* file, which defines the top level modules (chapters) in this course. 

4. The starting point (index page) for the course is rendered from asciidoc content in the *$CONTENT_ROOT/modules/ROOT/pages/index.adoc* file.

5. Each top level module has a separate asciidoc file (*nav.adoc*) located in *$CONTENT_ROOT/modules/module_name/* folder. The *nav.adoc* lists the sections that make up the chapter/module.

6. Edit the asciidoc files under *$CONTENT_ROOT/modules/module_name/pages* folder for writing lectures and hands-on lab content as per the outline provided by the course architect/peoduct owner. You can use the *asciidoctor* plug-in preview plugin (Press *"Ctrl + Shift + V"* in VSCode) to preview the rendered HTML content.

7. To preview the rendered website as it would look for end-users consuming this content, do the following:

    * Run the **npm run watch:adoc** command to automatically detect changes to your asciidoc content and invoke the Antora HTML generator:

    ```bash
    $ npm run watch:adoc
    ```

    * In another termainal window, run the **npm run serve** command that starts a local web server that serves the generated HTML content:

    ```bash
    $ npm run serve
    ```
    You will be shown the local URL where you can view the rendered content. Open the link in a web browser.

    * Keep making changes in your asciidoc source files. The **npm watch** command will automatically detect your changes and re-generate the HTML content. Refresh your web browser to view the updated content

8. Once you are satisfied with how the HTML content is rendered locally in your workspace, you can commit your changes and do a **git push** to push your content to the **main** branch of the course Git repository. An automated GitHub action runs on every push to the **main** branch and updates the HTML content in GitHub Pages.

9. After a few minutes, the GitHub action finishes and you can view the latest rendered asciidoc content at https://rsriniva.github.io/rhods-quick-course.

10. If you run into any issues, report bugs/suggestions/improvements about this course here - https://github.com/rsriniva/rhods-quick-course/issues
