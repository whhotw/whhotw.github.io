---
layout: post
title: "upgrade RN version from 0.57.8 to 0.59.10"
date: 2019-10-12 20:38:43 +0800
comments: true
categories: react-native
---
Change react-native version to `0.59.0` manually.

```
"dependencies": {
	"react-native": "0.59.0",
}
```

And run `yarn install` & `yarn upgrade 0.59.10`

if got error message as below

```
Undefined symbols for architecture x86_64:
  "_JSClassCreate", referenced from:
      facebook::jsc::JSCRuntime::createObject(std::__1::shared_ptr<facebook::jsi::HostObject>)::$_0::operator()() const in libReact.a(JSCRuntime.o)
      facebook::jsc::JSCRuntime::createFunctionFromHostFunction(facebook::jsi::PropNameID const&, unsigned int, std::__1::function<facebook::jsi::Value (facebook::jsi::Runtime&, facebook::jsi::Value const&, facebook::jsi::Value const*, unsigned long)>)::$_1::operator()() const in libReact.a(JSCRuntime.o)
  "_JSContextGetGlobalObject", referenced from:
      facebook::jsc::JSCRuntime::global() in libReact.a(JSCRuntime.o)
      facebook::jsc::JSCRuntime::createFunctionFromHostFunction(facebook::jsi::PropNameID const&, unsigned int, std::__1::function<facebook::jsi::Value (facebook::jsi::Runtime&, facebook::jsi::Value const&, facebook::jsi::Value const*, unsigned long)>)::HostFunctionMetadata::initialize(OpaqueJSContext const*, OpaqueJSValue*) in libReact.a(JSCRuntime.o)
  "_JSEvaluateScript", referenced from:
      facebook::jsc::JSCRuntime::evaluateJavaScript(std::__1::unique_ptr<facebook::jsi::Buffer const, std::__1::default_delete<facebook::jsi::Buffer const> >, std::__1::basic_string<char, std::__1::char_traits<char>, std::__1::allocator<char> > const&) in libReact.a(JSCRuntime.o)
  "_JSGlobalContextCreateInGroup", referenced from:
      facebook::jsc::JSCRuntime::JSCRuntime() in libReact.a(JSCRuntime.o)
      facebook::jsc::JSCRuntime::JSCRuntime() in libReact.a(JSCRuntime
...
```

Remember add `JavaScriptCore.framework` to project

#Upgrade-helper

It can find out differences between the two versions.

https://react-native-community.github.io/upgrade-helper
