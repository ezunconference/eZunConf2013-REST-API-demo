# eZ Publish REST Demo

This repository contains a very rough example of the usage of the REST API in
JavaScript presented at [the eZ Unconf #2 in
2013](http://share.ez.no/blogs/ez/ez-unconference-2-look-back-at-the-event-slides-and-pics).

The application allows to take a picture with the webcam of the computer and to
create the corresponding content in the eZ Publish repository with the REST API!

## Requirements

  * a recent eZ Publish 5 install (5.1 or 2013.04, might also work with an earlier
    versions)
  * a modern browser [supporting getUserMedia/stream
    API](http://caniuse.com/stream)
  * a computer with a webcam

## Install

  * Clone this Git repository
  * Copy or symlink the `demorest` folder into the `web` folder of eZ Publish
  * If you installed [the rewrite rules for a virtual host
    setup](https://confluence.ez.no/display/EZP51/Virtual+host+setup), you need
    to add the following rewrite rule right before `RewriteRule .* /index.php`:

    ```apache
    RewriteRule ^/demorest/ - [L]
    ```

## Usage

  * Go to http://<ezpublish-url>/demorest/
  * The browser should ask for the permission to use the webcam
  * Click on *Capture!* to take a picture with your webcam
  * In *Your profile* part, fill a name and click on *Publish*
  * The first time you click on *Publish*, the browser should ask for a login
    and a password of an eZ Publish user with the permission to create content
  * The log part in the right should fill itself with messages and at the end of
    the publish operation, a link to the newly created content should be
    available

Here are the results in one screenshot:

![Screenshot of the app](https://github.com/ezunconference/eZunConf2013-REST-API-demo/raw/master/screenshot.png)
