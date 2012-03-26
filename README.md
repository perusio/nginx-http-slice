# Nginx HTTP Slice module

## Introduction 

This is a module that is distributed with
[tengine](http://tengine.taobao.org) which is a distribution of
[Nginx](http://nginx.org) that is used by the e-commerce/auction site
[Taobao.com](http://en.wikipedia.org/wiki/Taobao). This distribution
contains some modules that are new on the Nginx scene. The
`ngx_http_slice_module` module is one of them.

This module can be thought out as a *reverse byte-range* request
header. It's main utility is to allow Nginx to slice a big file in
small pieces (byte-ranges) while permitting to use on-the-fly gzip
compression.

A typical example is for allowing someone to download a large video
file while keeping the bandwith usage minimal. This might also be used
as device for selling a video file by pieces where each link points to
different zones of the file splitted by file ranges.

Other use would be to use a generic CSS file and use only part of it
for each section of a site. Granted that byte-range slicing isn't the
most intuitive for such.

Note also that using arguments is more **useful** than byte-ranges in
the sense that they can be set in a normal link, while byte ranges
require a special [HTTP header](https://en.wikipedia.org/wiki/Byte_serving).


## New Repository

The new repo is at
[https://github.com/taobao/nginx-http-slice](https://github.com/taobao/nginx-http-slice).
