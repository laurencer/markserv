#markserv

##What is it?

markserv lets you edit markdown documents and view the changes in your web browser, realtime! markserv saves your scroll position in the browser as you edit :)

##Why is it?

markserv is designed to replace a MAMP + Marked2 workflow. 

I purchased [Marked2](http://marked2app.com/) after seeing a colleage use it to edit markdown content. It looked awesome, but it felt clunky. And it didn't integrate with my almost constant CLI usage. While I found Marked2 to have a very well-rounded feature set, it was simply too slow, and too memory intensive.

So...

I put some _Node.js_ on it :)

![Skateboarding Dog](http://media.giphy.com/media/yN6TNQhiIxeW4/giphy.gif)

##Features

 - An HTTP server that Renders markdown files in HTML
 - GitHub flavor CSS to your markdown files on the fly
 - GitHub style syntax highlighting 
 - Follows links to markdown files
 - Rendered page updates every time the markdown file is changed
 - Scroll position is saved so you don't loose your position while you edit


##Pre-Requisites

 - Node.js & NPM
 - Web Browser
 - Text Editor

##Installation

Install the markserv server via npm.

```shell
npm install markserv
```

##Usage

Change to the directory of your CLI

    cd path/to/serve/from

Start the HTTP markdown server on port 8080

    markserv ./

Point your browser to README.md

![Expected output](http://i.imgur.com/yWv8dGZ.png)

###Realtime/Live editing

Edit your markdown file, and you should now see the page reloading as you save your Markdown file. It should save your scroll position, which helps when editing extemely large documents.

![Live editing example](http://i.imgur.com/duvFBOF.gif)


###Linking to an external Markdown file

You can link to an external Markdown file in the same way that you use GitHub Wiki links. You can use the example code here to see how external links work.

Example code:

```md
[Skateboarding Dog!](Linked-Markdown-Example)
```

Example link:

[Skateboarding Dog!](Linked-Markdown-Example)


##How does it work?

markserv watches for file updates to the markdown file, and to the CSS directory, and autoamatically reloads the Markdown page via websockets. markserv remembers the scroll position you were at in the web browser, and reloads the page with the same scroll position when you make changes.

markserv was built for working on projects that contain a combination of web content and Markdown, where the markdown gets reloaded on the fly as the file is saved in your text editor. But it also serves regular HTTP content, replacing the need for a more bulky web server setup using MAMP, etc.