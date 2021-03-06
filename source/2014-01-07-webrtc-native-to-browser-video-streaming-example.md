---
title: WebRTC Native C++ to Browser Video Streaming Example
date: 2014-01-07 07:17:48
tags: WebRTC, Programming, Code, CPP
author: Kam Low
author_site: https://plus.google.com/+KamLow
layout: article
---

![WebRTC](logos/webrtc-250x250.png "WebRTC"){: .align-left}
There is a lot of information out there about browser to browser WebRTC streaming, but surprisingly there is not much coverage on how to stream video from a native application to the browser. Hopefully this example will be of some use to those of you out there who are looking to use WebRTC in native applications.

We have repackaged the `peerconnection_client` and `peerconnection_server` projects from the WebRTC repository with a few modifications, and included a `native-to-browser-test.html` page which you can use to view the native video stream in your browser.

Follow the steps below to get the sample working:

1. Checkout and build the WebRTC repository as per the [official guide](http://www.webrtc.org/reference/getting-started)
2. Clone or [download the example repository](https://github.com/auscaster/webrtc-native-to-browser-peerconnection-example) from Github: `git clone https://github.com/auscaster/webrtc-native-to-browser-peerconnection-example.git`
3. Copy the `peerconnection` folder into the `webrtc/trunk/talk/examples` folder, ensuring to rename and backup the existing `peerconnection` folder
4. Build the WebRTC solution again
5. Run the `peerconnection_server` and `peerconnection_client` executables located in `webrtc/trunk/build`
6. Fire up the `native-to-browser-test.html` page in Chrome
7. Select the "myclient" entry from the `peerconnection_client` window to begin broadcasting video to the browser page
8. If all went according to plan you should see your sexy self in the browser!

Note that this example only works in Chrome, as the DTLS SRTP signalling which is required by Firefox is not implemented. If you want to stream to both Chrome and Firefox then take a look at the [Symple](/symple) project, which features a native C++ server sample that streams live video to the browser using a Node.js server for signalling. Also check out the [Anionu SDK](https://github.com/anionu/anionu-sdk), which features a native WebRTC plugin for cross-browser video streaming using Anionu's Spot client.

Hopefully you found this information useful. Keep sharing the love!