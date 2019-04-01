# Node JS

```
npm list // list all dependencies
npm list --depth=0 // only your app dependency

npm outdated
npm i npm-check-updates
npm un -g jquery // uninstall 
```

## Publishing a package

```
npm adduser // if not registered
npm login // already registered
npm publish

// update already published package
npm version major
npm version minor
npm version patch
npm publish
```

## Set port

```
// mac
export PORT=5000
// windows
set PORT=5000
```

## Query params & string

```
req.params
req.query
```

## Validation

```
npm i joi
```

## Middleware

```javascript
app = express()

app.use((req, res, next) => {
	// do something
	next();
})
````

```javascript
// Sample 
app.use(express.json());
app.use(express.urlencoded({extended: true})); // name=hemant&age=20
app.use(express.static('public'));

// security
app.use(helmet())

// logging
app.use(morgan())
```

## Environment

```javascript
process.env.NODE_ENV // undefined - if not set
// OR
app.get('env') // development - if not set
```

## Manage config

https://www.npmjs.com/package/config

```
npm install config
```


 
