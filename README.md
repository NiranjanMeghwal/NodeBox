# NodeBox : Decentralized file storage system based on IPFS and Blockchain

### To run the project:
* clone this repo
* start Ganache and log in to Matamask wallet

then run : 
```
npm i
npm run start 
truffle migrate --reset
```

Finished webpage :

![finished_webpage](https://github.com/NiranjanMeghwal/NodeBox/blob/main/1.JPG)

You can now add files, after completing transactions the file gets successfully stored onto the blockchain with the help of IPFS:

![uploaded files](https://github.com/NiranjanMeghwal/NodeBox/blob/main/5.JPG)

!!! NOTE:

As of 10 August 2022, Infura has been upgraded and it's not possible to upload files via their public URLs. Users should now provide:
* project id (from infura IPFS)
* API key scret (from infura IPFS)

[For more Info visit this page.](https://blog.infura.io/post/ipfs-public-api-and-gateway-deprecation)

to get desired results, update /src/components/App.js : 

```
const auth = 'Basic ' + Buffer.from('user_project_id' + ':' + 'api_key_secret').toString('base64')
// this sets up the auth header to send 

var ipfs = ipfsHttpClient.create({
  host: 'ipfs.infura.io',
  port: 5001,
  protocol: 'https',
  apiPath:'/api/v0',
  headers: {
    authorization: auth
    }
});
```
