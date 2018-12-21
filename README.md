<div align="center">
    <img src="./assets/redis-js.png" width="50%" height="75%"/>
</div>

# About

A simple Mongoose Redis caching module.

# Installation

```sh
npm i mongoose-redis-caching
```

OR

```sh
yarn add mongoose-redis-caching
```

# Usage

Require in the module

```javascript
const mongoose = require('mongoose')
const mongooseRedisCaching = require('mongoose-redis-caching')
```

Configure your mongoose caching instance

```javascript
mongooseRedisCaching(mongoose)
```

Add your own Redis URL to your __.env__ file. The default is set to your local redis instance.

Then use as below (with Caching):

```javascript
const blogs = await Blog.find({ _user: req.user.id }).cache()
```

Use as below with a set time (in seconds) for cached item to expire:

```javascript
const blogs = await Blog.find({ _user: req.user.id }).cache(60)
```

The default time is 60 seconds if no time is provided.

Use as below (without Caching):

```javascript
const blogs = await Blog.find({ _user: req.user.id })
```

# Coming soon

- [x] Expire items
- [ ] Compression of items stored on Redis