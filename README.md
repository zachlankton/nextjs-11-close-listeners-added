# REPRO: MaxListenersExceededWarning: Possible EventEmitter memory leak detected. 11 close listeners added to

This code is a reproduction of the above error.

Steps:

- Clone
- npm install
- npm build
- npm start
- load site in a browser at least once (doesn't do it if not)
- CTRL-C 11 times
- Error below gets produced

```bash
zach@zach-ubuntu-office:~/RSC/nextjs$ npm start

> nextjs@0.1.0 start
> next start

   ▲ Next.js 14.1.0
   - Local:        http://localhost:3000

 ✓ Ready in 226ms
^C^C^C^C^C^C^C^C^C^C^C(node:2035457) MaxListenersExceededWarning: Possible EventEmitter memory leak detected. 11 close listeners added to [Server]. Use emitter.setMaxListeners() to increase limit
(Use `node --trace-warnings ...` to show where the warning was created)
^C^C^C

```
