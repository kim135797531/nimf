---
layout: page
title: Nimf
---

Nimf is an input method framework available for GNU/Linux. Nimf has a
module-based client-server architecture in which an application acts as a
client and communicates **synchronously** with the Nimf server via a
**unix socket**. Nimf provides

* Input Method Server
  * `nimf-daemon` including IMdkit(XIM)
* Language Engines
  * Chinese (in alpha stage, based on sunpinyin, libchewing, librime)
  * Japanese (in alpha stage, based on anthy)
  * Korean (based on libhangul)
* Client Modules
  * GTK+2, GTK+3, Qt4, Qt5
* Indicator
  * `nimf-indicator` for Unity, GNOME Panel, KDE
* Settings tool to configure the Nimf
  * `nimf-settings`
* Development files
  * C library and headers
  * GObject introspection data file for language bindings
