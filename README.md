# Better SSE

A dead simple, dependency-less, spec-compliant server-side events implementation for Node, written in TypeScript.

This package aims to be the easiest to use, most compliant and most streamlined solution to server-side events with Node that is framework agnostic and feature rich.

[See the WHATWG standards section for server-sent events.](https://html.spec.whatwg.org/multipage/server-sent-events.html)

[See the MDN guide to server-sent events.](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events)

# Installation

```bash
# npm
npm install better-sse

# Yarn
yarn add better-sse
```

_Better SSE ships with types built in. No need to install from `@types` for TypeScript users!_

# Basic Usage

Better SSE has compatibility with many different frameworks and libraries, but is commonly used by users implementing an application with the [Express framework](http://expressjs.com/).

See the recipes section of the documentation for use with other frameworks and libraries.

```javascript
// Server
import sse from "better-sse";

app.get("/sse", sse(), (req, res) => {
	res.push("speak", "Hello, world!");
});
```

```javascript
// Client
const sse = new EventSource("/sse");

sse.addEventListener("speak", ({data}) => {
	console.log(data);
});
```

Check the API documentation for information on getting more fine-tuned control over your data such as managing event IDs, data serialization, streams, dispatch controls and more!

# License

This project is licensed under the MIT license.
