## 1. unable to get local issuer certificate
This is valide for me.
```
set NODE_TLS_REJECT_UNAUTHORIZED=0
```
answer from here (https://stackoverflow.com/questions/36494336/npm-install-error-unable-to-get-local-issuer-certificate)

## 2. RequestError: read ECONNRESET

Set the electron mirror to `taobao`.
```
export ELECTRON_MIRROR=https://npm.taobao.org/mirrors/electron/
```
but `taobao` haven't version `16.07` (please check the version by yourself).

## 3. 
Indicat the `electron` when donwload.

```
npm install --save-dev electron@16.0.6 --verbose
```

## 4. output

```
> electron@16.0.6 postinstall /Users/xxx/prj/my-electron/node_modules/electron
> node install.js

(node:10812) Warning: Setting the NODE_TLS_REJECT_UNAUTHORIZED environment variable to '0' makes TLS connections and HTTPS requests insecure by disabling certificate verification.
(Use `node --trace-warnings ...` to show where the warning was created)
npm verb lifecycle electron@16.0.6~postinstall: unsafe-perm in lifecycle true
npm verb lifecycle electron@16.0.6~postinstall: PATH
```
