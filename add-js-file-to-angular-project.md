# Add lib js file to angular project
example web DAV
1. Add file to assset or dist or nodemodule

![assset/webDAV][ss1]

2. Add script to angular.json or import in component in needed
   
method 1: import to component
```ts
 import * as ITHit from 'assets/webDAV/ITHitWebDAVClient.js'; 
```
method2: import to angular.json
![angular_json][ss2]




3. Use in component

declare
```ts
declare const ITHit;
```
![angular_json][ss3]


[ss1]: assset/webDAV.PNG
[ss2]: assset/angular_json.PNG
[ss3]: assset/useWebDAV.PNG
