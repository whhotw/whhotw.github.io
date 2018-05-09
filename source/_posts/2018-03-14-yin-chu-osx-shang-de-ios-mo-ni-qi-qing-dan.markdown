---
layout: post
title: "印出 OSX 上的模擬器"
date: 2018-03-14 11:04:15 +0800
comments: true
categories: 
---
```
▶ xcrun simctl list devices
== Devices ==
-- iOS 9.3 --
-- iOS 10.1 --
-- iOS 11.2 --
    iPhone 8 (C34476E5-474D-4295-B113-07A1C9A58F7C) (Booted)
    iPhone 8 Plus (7D2939FA-6C7C-4ECC-91BA-B81245193273) (Shutdown)
    iPhone SE (F6FC4EB2-57A8-43A5-B3DF-3C2D0D86EAB5) (Shutdown)
    iPhone X (CF6EAD3A-D89A-416B-9E22-A9FEE01FABC0) (Shutdown)
-- tvOS 11.2 --
-- watchOS 4.2 --
    Apple Watch - 38mm (762755FE-F880-4D3F-AC59-5273E136AA22) (Shutdown)
    Apple Watch - 42mm (9C46B910-2347-4632-87C1-4CB7C146A7DA) (Shutdown)
    Apple Watch Series 3 - 38mm (1636D402-593A-4E43-8936-5F8269FC8E06) (Shutdown)
    Apple Watch Series 3 - 42mm (F44308B7-7EE5-451E-A5BE-47C4AF6D2182) (Shutdown)
-- Unavailable: com.apple.CoreSimulator.SimRuntime.iOS-10-3 --
    iPhone 7 Plus (93B3F053-7A69-462B-995C-FDBB0DECD696) (Shutdown) (unavailable, runtime profile not found)
    iPad Air (D32532AE-CAD0-4A33-B5C3-D7D6603CD14A) (Shutdown) (unavailable, runtime profile not found)
-- Unavailable: com.apple.CoreSimulator.SimRuntime.iOS-11-1 --
    iPad Air (458272DE-23F5-4402-9499-38D34EE0C2C4) (Shutdown) (unavailable, runtime profile not found)
-- Unavailable: com.apple.CoreSimulator.SimRuntime.watchOS-3-1 --
    Apple Watch - 38mm (F517E442-BA3D-414E-8AC6-DC3DADEBBBA5) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch - 42mm (77DAED46-0C55-4BF1-BEFB-29CFBF1878B9) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 2 - 38mm (3BC9851A-B5F0-4388-AB2F-970615C09131) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 2 - 42mm (D96A8FAE-A911-4F6E-B410-394F612D72A5) (Shutdown) (unavailable, runtime profile not found)
-- Unavailable: com.apple.CoreSimulator.SimRuntime.watchOS-3-2 --
    Apple Watch - 38mm (79FE64E2-6561-460D-B3B2-85D6E27E504C) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch - 42mm (FAEC2DB5-99B5-406A-A9B9-2CCD0280802B) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 2 - 38mm (56BE61D3-3CDD-44CD-A383-C4B72F862A7F) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 2 - 42mm (D01D1358-9E50-4DCC-B1A0-58A1AED5A57A) (Shutdown) (unavailable, runtime profile not found)
-- Unavailable: com.apple.CoreSimulator.SimRuntime.watchOS-4-1 --
    Apple Watch - 38mm (83E57EAD-BC33-4ADA-AC43-C70DE030CB13) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch - 42mm (45F4AB4B-CEFB-4F88-8ADD-B491E8AEDB51) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 2 - 38mm (DE82F3F9-0B17-4914-A146-CE8B047A0D32) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 2 - 42mm (1B69D57E-707E-4458-9A38-0142FADE86B4) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 3 - 38mm (8F4B32E9-EBC3-46F8-B1A1-F30C8D863F65) (Shutdown) (unavailable, runtime profile not found)
    Apple Watch Series 3 - 42mm (586539F8-FE12-4354-A102-3A17F71E867A) (Shutdown) (unavailable, runtime profile not found)
```