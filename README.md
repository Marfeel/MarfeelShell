# MarfeelShell

Disclaimer |
---------- |
This is a simplified version of the MarfeelShell. in order to make everything more understandable, we have removed some superfluous parts and we have splitted the server-rendered html in [components](https://github.com/Marfeel/MarfeelShell/tree/master/layouts/partials). Anyway, you can always visit the [Complete version](https://bc.marfeel.com/truththeory.com/index.html?marfeeldt=s&marfeelgarda=off)

MarfeelShell is a PWA that uses AMP Shadow (loaded from `k.s.js`) to use AMP docs to show the app views.

The `shadow-v0.js` file being used is a modified version that instantiates an AMPDocShell ([ampproject/amphtml#9638](https://github.com/ampproject/amphtml/pull/9638)). This way AMP extensions can be used at Shell level.

One key component is the `amp-shadow-doc-loader` ([sections-model.html](https://github.com/Marfeel/MarfeelShell/blob/master/layouts/partials/sections-model.html), [ampproject/amphtml#9639](https://github.com/ampproject/amphtml/pull/9639)). This AMP extension is the responsible to load an AMP doc leaf using the AMP Shadow `attachShadowDoc` API. Encapsualting this call inside an AMP extension allows the AMP runtime to manage the fetching, DOM manupulation etc... as the user navigates.

`k.s.js` boots the Shell, contains all the logic for UI orchestration (navigation levels, swiping, etc...), and other PWA features (caching, push notifications, offline, etc...).