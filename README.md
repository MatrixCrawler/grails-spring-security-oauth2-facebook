Spring Security OAuth2 Facebook Plugin
======================================
[ ![Download](https://api.bintray.com/packages/matrixcrawler/plugins/spring-security-oauth2-facebook/images/download.svg) ](https://bintray.com/matrixcrawler/plugins/spring-security-oauth2-facebook/_latestVersion)

Add a Google OAuth2 provider to the [Spring Security OAuth2 Plugin](https://github.com/MatrixCrawler/grails-spring-security-oauth2).

Installation
------------
Add the following dependencies in `build.gradle`
```
dependencies {
...
    compile 'org.grails.plugins:spring-security-oauth2:1.1+'
    compile 'org.grails.plugins:spring-security-oauth2-facebook:1.0.0'
...
}
```

Usage
-----
Add this to your application.yml
```
grails:
    plugin:
        springsecurity:
            oauth2:
                providers:
                    google:
                        api_key: 'facebook-api-key'               #needed
                        api_secret: 'facebook-api-secret'         #needed
                        successUri: "/oauth2/facebook/success"    #optional
                        failureUri: "/oauth2/facebook/failure"    #optional
                        callback: "/oauth2/facebook/callback"     #optional
```
You can replace the URIs with your own controller implementation.

In your view you can use the taglib exposed from this plugin and from OAuth plugin to create links and to know if the user is authenticated with a given provider:
```xml
<oauth2:connect provider="facebook" id="google-connect-link">Facebbok</oauth2:connect>

Logged with facebook?
<oauth2:ifLoggedInWith provider="facebook">yes</oauth2:ifLoggedInWith>
<oauth2:ifNotLoggedInWith provider="facebook">no</oauth2:ifNotLoggedInWith>
```
License
-------
Apache 2