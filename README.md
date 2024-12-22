# Cryptix gRPC interface

Cryptix gRPC module is a basic request/response wrapper for interfacing with [Cryptixd](https://github.com/cryptix-network/cryptixd)

## Cloning cryptix-grpc

```
git clone https://github.com/cryptix-network/cryptix-grpc
cd cryptix-grpc
npm install
```

## Example

```js
const { Client } = require('@cryptix/grpc');

const client = new Client({
    host:"127.0.0.1:18210"
});
client.connect();
client.verbose = true;

try {
    let response = await client.call('getMempoolEntriesRequest', { });
    console.log(response);
} catch(ex) {
    ...
}

client.call('getVirtualSelectedParentBlueScoreRequest', { }).then((response)=>{
    console.log(response);
}).catch((err)=>{
    console.log('error:',err);
})
```
