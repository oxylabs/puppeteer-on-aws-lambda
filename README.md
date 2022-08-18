# puppeteer-on-aws-lambda
Puppeteer on AWS Lambda

```bash
"zip": "npm run build && 7z a -r function.zip ./dist/*  node_modules/",
"sendToLambda": "npm run zip && aws s3 cp function.zip s3://chrome-aws && rm function.zip && aws lambda update-function-code --function-name puppeteer-examples --s3-bucket chrome-aws --s3-key function.zip"
```

```node
`npm i --save chrome-aws-lambda puppeteer-core`
```

```javascript
const browser = await chromium.puppeteer
        .launch({
            args: chromium.args,
            defaultViewport: chromium.defaultViewport,
            executablePath: await chromium.executablePath,
            headless: chromium.headless
        });
```
