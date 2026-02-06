---
author: "dlowrenz"
title: "What file upload: multiple"
date: "2025-06-19"
description: "One of my many articles."
tags: [
    "markdown",
    "text",
]
draft: true
---
## A Serious Headache: TL;DR

I perform like a solutions architect with a backend engineer day-to-day job. Also doing some documentations, yeah I know some of us hate docus, that allow me to walk any engineer through a feature I am working on. Currently I program in a serverless framework using nodejs. And I was tasked to do a multiple file uploading because the previous maintainer
did not do it for some reason. And we are having multiple issues about our single file uploading. That's on top of the "priority" tasks they've mentioned.

I started researching about it and how I can integrate it to serverless framework. Where in a single lambda function could handle a hard limit 10 mb of data in total at once or single invocation.

It might be a well-knowed problem. This task could be an easy peasy for other developers, making an HTTP file uploading. But how does file uploading works was my question. 

## What is file upload?
---
[File Upload](https://cloudinary.com/guides/front-end-development/file-upload-as-a-service-how-it-works-and-5-leading-solutions#:~:text=File%20uploads%20can%20be%20initiated,remote%20server%20or%20storage%20location) refers to the process of transferring digital files from a local device or machine to a remote server or storage location using a network. Given that, I need a solution to steamline the process.
The current design was there's a 2 api calling the `process file` and `store file`.

The upload api will be triggered and `process file` will take place and the `store file` will return the signedUrl and it's up to the Frontend/Client how to consume the data returned. I spent maybe 40 ci/cd pipelines going back and forth updating and testing the frameworks and libraries.

##### Libraries considered

* [multer](https://www.npmjs.com/package/multer)
* [busboy](https://www.npmjs.com/package/busboy)
* Just don't do it





#### Code block with backticks

```
html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
```

{{< css.inline >}}
<style>
.canon { background: white; width: 100%; height: auto; }
</style>
{{< /css.inline >}}
