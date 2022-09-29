# storj-s3-presign-nodejs

Example project to show how to upload using presign urls using the [AWS S3 V3 Client](https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/clients/client-s3/index.html) with [Storj](https://storj.io)

In the project directory, run:
```
npm start
```
Runs the app in the development mode.

# Walk through video

https://www.youtube.com/watch?v=F6LdiDzitFo

# Test with Curl
First request the presigned url from the express endpoint, including a `key` param for the filename.
```bash
curl -X POST http://localhost:3001/presign -d 'key=storj-tree.png'
```
Response
```
{"url":"<presigned url>"}%                               
```

Then use curl to upload a file to [Storj](https://storj.io)
```bash
curl -X PUT --data-binary @storj-tree.png -H 'Content-Type: image/png' <presigned url>
```

# Frontend code

In addition to curl you can also upload using a static site site in the browser.

https://github.com/amozoss/storj-s3-presign-react


