# __Ways of connecting Node + React__

## 1. Server Hosts Node API + React SPA
+ Node(Express) API handles incoming requests
+ Requests not targeting API routes return React SPA
+ Data is exchanged between React app and Node API in JSON format

## 2. Two Separated Servers
+ Node(Express) API handles incoming requests
+ React SPA served from separate static host
+ Data is exchanged between React app and Node API in JSON format.

## In both cases
+ will make logically Seperated Apps(SPA + API)
+ has better performance than using Template server(EJS, Pug, ...)