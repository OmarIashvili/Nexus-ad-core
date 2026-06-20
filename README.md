# Nexus Ad-Core
**Nexus Ad-Core** is a high-performance, low-latency ad delivery engine specifically designed for **Unity 6**. It solves the problem of frame drops and latency typically associated with third-party ad SDKs.

## The Problem
Modern mobile games require 60fps consistency. Most ad SDKs force the main thread to wait for network responses or perform heavy UI layout passes, resulting in dropped frames and poor player experience.

## Our Solution
Nexus Ad-Core implements:
* **Asynchronous Initialization:** Zero impact on the game's startup sequence.
* **Frame-Budget Monitoring:** Ad calls are dynamically adjusted based on the current device frame time.
* **Native-Bridge Design:** Direct rendering path to avoid Webview tax.

## Technical Prototype
You can see the engine architecture and real-time performance metrics here:
[https://tubular-granita-7982ef.netlify.app/](https://tubular-granita-7982ef.netlify.app/)

## Quick Start (C#)
```csharp
// Initialize Nexus Core
NexusAdManager.Instance.Initialize();

// Request an ad without blocking the main render loop
await NexusAdManager.Instance.RequestAdAsync();
