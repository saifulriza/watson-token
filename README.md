## Warning

Don't use this package for production. your apikey will exposed when program generating token

## Installation

```
npm i watson-token
```

## How to use

```
generateToken(
    DOMAIN,
    PATH,
    PORT,
    APIKEY,
    CALLBACK
  );
```

| name     | type     |
| -------- | -------- |
| DOMAIN   | string   |
| PATH     | string   |
| PORT     | number   |
| APIKEY   | string   |
| CALLBACK | function |

## Example

```
import generateToken from "watson-token";
generateToken(
    "proxy-watson.herokuapp.com", // your domain proxy for bypassing cors
    "/identity/token", // path of your proxy
    "80", // port of your proxy. default is 80
    "iGjNmBnh6rTw4P5EEk_5rYchhsQgtILxaJY0GAZk5Loo", //your apiKey
    (response) => {
     console.log(response); //get your generated key
    }
  );
```

<<<<<<< HEAD
if you want ot create your own proxy, you can just copy paste this short code :
=======

## Proxy

if you want to create your own proxy, you can just copy paste this short code :

> > > > > > > watson token generator

```
const express = require("express");
const cors = require("cors");
const { createProxyMiddleware } = require("http-proxy-middleware");
const app = express();
const PORT = process.env.PORT || 3000;
app.use(cors());
app.use(
  "/identity/token",
  createProxyMiddleware({
    target: "https://identity-1.eu-central.iam.cloud.ibm.com",
    changeOrigin: true,
  })
);
app.listen(PORT);
```

<<<<<<< HEAD
make sure you have installed express (npm install express), cors (npm install cors) and http-proxy-middleware (npm i http-proxy-middleware).
=======
make sure you have installed express (npm install express), cors (npm install cors) and http-proxy-middleware (npm i http-proxy-middleware) to run this code.

> > > > > > > watson token generator
> > > > > > > for complete documentation of http-proxy-middleware you can find [here!](https://github.com/chimurai/http-proxy-middleware#readme)
