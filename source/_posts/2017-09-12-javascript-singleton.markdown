---
layout: post
title: "JavaScript Singleton"
date: 2017-09-12 09:52:10 +0800
comments: true
categories: javascript
---
[參考](http://www.dofactory.com/javascript/singleton-design-pattern)

```
var Singleton = (function () {
    var instance;
 
    function createInstance() {
        var object = new Object("I am the instance");
        return object;
    }
 
    return {
        getInstance: function () {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();
 
function run() {
 
    var instance1 = Singleton.getInstance();
    var instance2 = Singleton.getInstance();
 
    alert("Same instance? " + (instance1 === instance2));  
}
```