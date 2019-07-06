---
layout: post
title: "Upgrade React-Native Version."
date: 2019-04-10 23:34:34 +0800
comments: true
categories: react-native
---
```
~ react-native-git-upgrade 0.59.3
git-upgrade info Check for updates
git-upgrade info Using yarn 1.10.1
git-upgrade info Read package.json files
git-upgrade info Check declared version
git-upgrade info Check matching versions
git-upgrade info Check React peer dependency
git-upgrade info Check that Git is installed
git-upgrade info Get information from NPM registry
git-upgrade info Upgrading to React Native 0.59.3, React 16.8.3
git-upgrade info Setup temporary working directory
git-upgrade info Configure Git environment
git-upgrade info Init Git repository
git-upgrade info Add all files to commit
git-upgrade info Commit current project sources
git-upgrade info Create a tag before updating sources
git-upgrade info Generate old version template
git-upgrade ERR! An error occurred during upgrade:
git-upgrade ERR! Error: Couldn't find preset "module:metro-react-native-babel-preset" relative to directory "/Users/whh/FUNBLOCK"
    at /Users/whh/.config/yarn/global/node_modules/babel-core/lib/transformation/file/options/option-manager.js:293:19
    at Array.map (<anonymous>)
    at OptionManager.resolvePresets (/Users/whh/.config/yarn/global/node_modules/babel-core/lib/transformation/file/options/option-manager.js:275:20)
    at OptionManager.mergePresets (/Users/whh/.config/yarn/global/node_modules/babel-core/lib/transformation/file/options/option-manager.js:264:10)
    at OptionManager.mergeOptions (/Users/whh/.config/yarn/global/node_modules/babel-core/lib/transformation/file/options/option-manager.js:249:14)
    at OptionManager.init (/Users/whh/.config/yarn/global/node_modules/babel-core/lib/transformation/file/options/option-manager.js:368:12)
    at compile (/Users/whh/.config/yarn/global/node_modules/babel-register/lib/node.js:103:45)
    at loader (/Users/whh/.config/yarn/global/node_modules/babel-register/lib/node.js:144:14)
    at Object.require.extensions.(anonymous function) [as .js] (/Users/whh/.config/yarn/global/node_modules/babel-register/lib/node.js:154:7)
    at Module.load (module.js:566:32)
git-upgrade ERR! Restore initial sources
```
因為 `.babelrc` 不符合預期，刪除檔案可以排除問題。
