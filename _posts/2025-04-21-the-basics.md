---
layout: post
title: The basics
permalink: /basic-concept
category: getting started
description: Learn about the configuration file and a sample view file.
---

## The basics

It use the JSON format.

Two things are essentials when building a UICX application.

### The configuration

```json
{
    "baseURL": "https://example.org/v1/",
    "webviewBaseURL": "https://example.org/",
    "deeplinks": {
        "/": "/home",
        "/article/(\d+)": "/article/$1"
        "/about": "/about"
    },
    "tapbar": {
        "Home": "/",
        "About": "/about",
        "Latest": "/article/last"
    },
    "preload": {
        "stylesheets": [ "https://example.org/style.css" ],
        "javascripts": [ "https://example.org/script.js" ]
    }
}
```

As you can see in this simple example the format is quite simple:

- in `baseURL` we define the base URL behind every API calls we will be doing
- in `webviewBaseURL` we define the base URL behind every WebView
- in `deeplinks` we define the app handled deeplinks its a map with the deeplink as key and the API path as value, you can use regular expressions inside
- in `tapbar` (_optional_) you can configure the app quick links
- in `preload` (_optional_) you can configure multiple `stylesheets` and `javascripts` files that should be downloaded locally to improve further page loading

### The pages

Behind every URL called by the app you MUST return a format repecting at least this structure:

```json
{
    "contentTemplate": "A complex HTML structure which will be injected in the HTML body tag of the WebView.",
    "headTemplate": "A complex HTML structure which will be injected in the HTML head tag of the WebView.",
    "stylesheets": [ "https://example.org/style.css" ],
    "javascripts": [ "https://example.org/script.js" ]
}
```

As you can see in the above example the format is quite simple:

- in `contentTemplate` we define the HTML that will be printed by the WebView inside the `<body>` tag
- in `headTemplate` we define the HTML that will be printed by the WebView inside the `<head>` tag
- in `stylesheets` and `javascripts` we define the files that must be included in the `<head>` (for stylsheets) and at the very end of the `<body>` (for the javascripts)