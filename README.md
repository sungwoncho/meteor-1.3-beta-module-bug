# Meteor 1.3 beta module bug

## Steps

1. Clone the repo and run.
2. App throws:

```
W20160221-21:38:04.880(11)? (STDERR)
W20160221-21:38:04.882(11)? (STDERR) /Users/mikecho/dev/meteor_projects/meteor-1.3-beta-module-bug/.meteor/local/build/programs/server/app/app.js:10
W20160221-21:38:04.883(11)? (STDERR) export {};                                                           // 1
W20160221-21:38:04.883(11)? (STDERR) ^^^^^^
W20160221-21:38:04.883(11)? (STDERR) SyntaxError: Unexpected reserved word
W20160221-21:38:04.883(11)? (STDERR)     at /Users/mikecho/dev/meteor_projects/meteor-1.3-beta-module-bug/.meteor/local/build/programs/server/boot.js:244:30
W20160221-21:38:04.884(11)? (STDERR)     at Array.forEach (native)
W20160221-21:38:04.884(11)? (STDERR)     at Function._.each._.forEach (/Users/mikecho/.meteor/packages/meteor-tool/.1.1.13-beta.11.1njovfl++os.osx.x86_64+web.browser+web.cordova/mt-os.osx.x86_64/dev_bundle/server-lib/node_modules/underscore/underscore.js:79:11)
W20160221-21:38:04.885(11)? (STDERR)     at /Users/mikecho/dev/meteor_projects/meteor-1.3-beta-module-bug/.meteor/local/build/programs/server/boot.js:140:5
=> Exited with code: 8
```

## Details

The following throws the above error:

```js
export {
};
```

While the following does not:

```js
export {
  undefined
}
```

The following also does not throw:

```js
import something from 'something';

export {
  something
}
```
