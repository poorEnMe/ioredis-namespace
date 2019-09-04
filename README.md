# ioredis-namespace

```js

const redisNs = require('ioredis-namespace');
const redisClient = redisNs.createClient('local', {
  port: 6379, // Redis port
  host: "127.0.0.1", // Redis host
  family: 4, // 4 (IPv4) or 6 (IPv6)
  password: "auth",
  db: 0
})
redisClient.get('a') // redis.get('local:a')
redisClient.set('b', 'valueB', 'EX', 60) // redis.get('local:b', 'valueB', 'EX', 60)

// Global
redisClient.getGlobal('a') // redis.get('global:a')
redisClient.setGlobal('b', 'valueB') // redis.setGlobal('global:b', 'valueB')

```