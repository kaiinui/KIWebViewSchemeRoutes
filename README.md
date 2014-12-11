KIWebViewSchemeRoutes
=====================

Routes a WebView's app scheme request such as `app://some_feature`

```objc
KISchemeRoutes *route = [KISchemeRoutes routesForScheme:@"app"];
[route addRoute:@"some_feature" then:^(NSDictionary *params) {
    // Do something.
}];
[route addCallbackRoute:@"camera" then:^(NSDictionary *params, KISchemeCallbackBlock callback) {
    // Do something.
    
    callback(returnParams)
}];

KIWebViewRoutingProxy *proxy = [KIWebViewRoutingProxy proxyWithRoute:route withOriginalDelegate:someDelegate];

self.webView.delegate = proxy;
```
