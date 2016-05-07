- [README](#readme)
  - [Installation](#installation)
  - [Configuration](#configuration)
    - [Org-capture and org-capture-pop-frame](#org-capture-and-org-capture-pop-frame)
    - [Firefox](#firefox)

# README<a id="orgf325292"></a>

org-capture-pop-frame is an extension of org-capture, when it is enabled,
org-capure will capture things in a new pop frame, after capture finish or abort.
the poped frame will be delete.

NOTE:

1.  This extension is suitable for capturing links and text in firefox.
2.  You can click with mouse in emacs header-line to finish or abort capture.

![img](./snapshots/org-capture-pop-frame.gif)

## Installation<a id="org997581a"></a>

org-capture-pop-frame is now available from the famous emacs package repo
[melpa](http://melpa.milkbox.net/), so the recommended way is to install it
through emacs package management system.

## Configuration<a id="orgd024d2d"></a>

### Org-capture and org-capture-pop-frame<a id="orgb21dc72"></a>

    (require 'org-capture)
    (require 'org-capture-pop-frame)
    (setq org-capture-templates
          '(("f" "org-capture-from-web" entry  (file+headline "~/note.org" "Notes-from-web")
             "** %a

    %i
    %?
    "
             :empty-lines 1)))

### Firefox<a id="org1248609"></a>

You need install **one** of the following firefox extensions, then config it.

1.  AppLauncher
    1.  Download links
        1.  <https://addons.mozilla.org/zh-CN/firefox/addon/applauncher/?src=api>
        2.  <https://github.com/nobuoka/AppLauncher>
    2.  Applauncher config
        1.  Name: org-capture(f) (Edit it)
        2.  Path: /home/feng/emacs/bin/emacsclient (Edit it)
        3.  Args: org-protocol://capture://f/&eurl;/&etitle;/&etext; ("f" is org-capture's key)
2.  org-mode-capture

    1.  Download links
        1.  <https://addons.mozilla.org/fr/firefox/addon/org-mode-capture/>
        2.  <http://chadok.info/firefox-org-capture>
    2.  Config it (Very simple, just change emacsclient path.)

    NOTE: The official org-mode-capture extension can not set some emacsclient options,
    for example: "&#x2013;socket-name" or "&#x2013;alternate-editor", you can use
    [my modify version of org-mode-capture](https://github.com/tumashu/firefox-org-capture),
    The xpi file can download from: <https://github.com/tumashu/firefox-org-capture/blob/master/org-capture-0.3.0.xpi?raw=true>
