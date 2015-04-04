# Youtube-dl PHP
A PHP wrapper for [youtube-dl](https://github.com/rg3/youtube-dl) tool.

[![Latest Stable Version](https://poser.pugx.org/norkunas/youtube-dl-php/v/stable.svg)](https://packagist.org/packages/norkunas/youtube-dl-php)
[![Latest Unstable Version](https://poser.pugx.org/norkunas/youtube-dl-php/v/unstable.svg)](https://packagist.org/packages/norkunas/youtube-dl-php)
[![License](https://poser.pugx.org/norkunas/youtube-dl-php/license.svg)](https://packagist.org/packages/norkunas/youtube-dl-php)

## Install
First step is to download the [youtube-dl](http://rg3.github.io/youtube-dl/download.html) and add it's path to
environment variables.

Second step is to install the wrapper using [Composer](http://getcomposer.org/):
```
composer require norkunas/youtube-dl-php
```

## Example
```php
use YoutubeDl\YoutubeDl;

$dl = new YoutubeDl([
    'continue' => true, // force resume of partially downloaded files. By default, youtube-dl will resume downloads if possible.
    'format' => 'bestvideo',
]);
// For more options go to https://github.com/rg3/youtube-dl#user-content-options

$dl->setDownloadPath('/home/user/downloads');
// $dl->setDebug(true);
$video = $dl->download('https://www.youtube.com/watch?v=oDAw7vW7H0c');
echo $video->getTitle(); // Will return Phonebloks
// $dl->getFile(); // \SplFileInfo instance of downloaded file
```

**Disabled options which would break download:**

list-formats, list-subs, list-thumbnails, get-url, get-title, get-id, get-thumbnail, get-description, get-duration, get-filename, get-format, dump-json, dump-single-json, print-json (used internally), newline, no-progress, console-title, verbose, dump-pages, write-pages, print-traffic, ignore-config (used internally).
