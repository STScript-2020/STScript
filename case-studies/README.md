# STScript: Case Studies

## Prerequisites
* [Node.js](https://nodejs.org/en/)
* Make sure no processes are listening on port 8080
  * For macOS/Linux users, run `sudo kill $(lsof -t -i :8080)`

## How to use
These instructions use the _Battleship_ case study as an example -- change the directory name and apply the same steps to the other case studies accordingly.

```bash
cd Battleship
```

To install dependencies and build the web application, run
```bash
npm install
npm run build
```

To start the web application, run
```bash
npm start
```
and visit http://localhost:8080 on your web browser.

As all case studies involve more than one client role,
open multiple web browser instances of http://localhost:8080 to interact with the multiparty protocol.
