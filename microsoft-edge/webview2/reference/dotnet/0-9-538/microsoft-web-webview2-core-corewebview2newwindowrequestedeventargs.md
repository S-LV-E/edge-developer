---
description: Embed web technologies (HTML, CSS, and JavaScript) in your native applications with the Microsoft Edge WebView2 control
title: 0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: Microsoft.Web.WebView2, Core, webview2, webview, dotnet, wpf, winforms, app, edge, CoreWebView2, CoreWebView2Controller, browser control, edge html, Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs
---

# 0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

Namespace: Microsoft.Web.WebView2.Core\
Assembly: Microsoft.Web.WebView2.Core.dll

Event args for the NewWindowRequested event.

## Summary

 Members                        | Descriptions
--------------------------------|---------------------------------------------
[Handled](#handled) | Whether the NewWindowRequestedEvent is handled by host.
[IsUserInitiated](#isuserinitiated) | IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.
[NewWindow](#newwindow) | Gets the new window.
[Uri](#uri) | The target uri of the NewWindowRequest.
[WindowFeatures](#windowfeatures) | Window features specified by the window.open call.
[GetDeferral](#getdeferral) | Obtain a CoreWebView2Deferral object and put the event into a deferred state.

The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)

## Members

#### Handled 

Whether the NewWindowRequestedEvent is handled by host.

> public bool [Handled](#handled)

If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy. If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load. Default is false.

#### IsUserInitiated 

IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.

> public bool [IsUserInitiated](#isuserinitiated)

#### NewWindow 

Gets the new window.

> public CoreWebView2 [NewWindow](#newwindow)

#### Uri 

The target uri of the NewWindowRequest.

> public string [Uri](#uri)

The target webview should not be navigated. If the NewWindow is set, its top level window will return as the opened WindowProxy.

#### WindowFeatures 

Window features specified by the window.open call.

> public CoreWebView2WindowFeatures [WindowFeatures](#windowfeatures)

These features can be considered for positioning and sizing of new webview windows.

#### GetDeferral 

Obtain a CoreWebView2Deferral object and put the event into a deferred state.

> public CoreWebView2Deferral [GetDeferral](#getdeferral)()

You can use the CoreWebView2Deferral object to complete the window open request at a later time. While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.

