# Rebuild Node Sass 

When building a project (it seems most often for the first time) sometimes
Node Sass needs to be rebuilt. At the console:

```
npm rebuild node-sass --force
```

This rebuilds node-sass.

## C++ Build Error (Windows)

The build can fail if VCBuild.exe is not installed. The error (edited for formatting):

```
Build FAILED.                                                                                                                                                                                
                                                                                                                                                                                             
"C:\Users\Thomas\code\easyjet-digital-lite\easyJet.Digital.Lite.Web\node_modules\node-sass\build\binding.sln"

(default target) (1) ->                                                        
(_src_\libsass target) ->                                                                                                                                                                    
  MSBUILD : error MSB3428: Could not load the Visual C++ component "VCBuild.exe". To fix this,
  1) install the .NET Framework 2.0 SDK,
  2) install Microsoft Visual Studio 2005 or
  3) add the location of the component to the system path if it is installed elsewhere.  [C:\Users\Thomas\code\easyjet-digital-lite\easyJet.Digital.Lite.Web\node_modules\node-sass\build\binding.sln]     
                                                                                                                                                                                             
    0 Warning(s)                                                                                                                                                                             
    1 Error(s)  
```

To fix this use NPM to install the *Windows Build Tools*:

```
npm install --global --production windows-build-tools
```

After this run ```npm rebuild node-sass --force``` again and it should work.