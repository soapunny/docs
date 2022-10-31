# __HTTPS Setting__

1. Download mkcert
```
  $ npm install --location=global mkcert
```

2. Create a Certificate Authority
```
  $ mkcert create-ca --help

    Usage: create-ca [options]

    Options:
        --organization [value]  Organization name (default: "Test CA")
        --country-code [value]  Country code (default: "US")
        --state [value]         State name (default: "California")
        --locality [value]      Locality address (default: "San Francisco")
        --validity [days]       Validity in days (default: 365)
        --key [file]            Output key (default: "ca.key")
        --cert [file]           Output certificate (default: "ca.crt")
        -h, --help              output usage information
```

3. Modify the server code
```js
    const https = require('https');
    import fs from "fs";

    const options = {
        key: fs.readFileSync('ca.key'),
        cert: fs.readFileSync('ca.crt')
    };

    console.log(`Server listening on port https://${HOST}:${PORT}`);
    https.createServer(options, app).listen(PORT);
```