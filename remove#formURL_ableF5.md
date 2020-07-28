# Remove # from url Angular 8 and deploy IIS, able to F5
1. app.routes.ts 
```ts
export const AppRoutes: ModuleWithProviders = RouterModule.forRoot(routes, {scrollPositionRestoration: 'top', useHash: false,});
```
2. app.module.ts 

```ts
providers: [{provide: LocationStrategy, useClass: PathLocationStrategy}]
```
3. Add rewrite module to IIS
https://download.microsoft.com/download/1/2/8/128E2E22-C1B9-44A4-BE2A-5859ED1D4592/rewrite_amd64_en-US.msi

![install rewirte module][ss1]
4. ng build --prod, and add file web.config in file build root

```xml
    
    <configuration>
        <system.webServer>
          <rewrite>
            <rules>
              <rule name="Angular Routes" stopProcessing="true">
                <match url=".*" />
                <conditions logicalGrouping="MatchAll">
                  <add input="{REQUEST_FILENAME}" matchType="IsFile" 
                     negate="true" />
                  <add input="{REQUEST_FILENAME}" ="IsDirectory" 
                    negate="true" />
                </conditions>
                <action type="Rewrite" url="./index.html" />
              </rule>
            </rules>
          </rewrite>
        </system.webServer>
    </configuration>
```

## Documentation  

https://angular.io/guide/deployment#routed-apps-must-fallback-to-indexhtml

`#removeHashAngular` `#remove#`

![nice][ss2]

[ss1]: assset/rewrite-module.PNG
[ss2]: assset/anime_girl_book_person_92295_1920x1080.jpg