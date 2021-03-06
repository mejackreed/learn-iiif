---
layout: page
title: Image API
permalink: /image-api/
---

The IIIF Image API is designed for standardization of requesting and delivering images on the Web. 

Like we saw earlier, that you can use it to embed an image in a webpage. Here is that example again.

<iframe width="100%" height="400" src="//jsfiddle.net/mejackreed/r3a5ayhe/2/embedded/result,html/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

This example uses the Image API to request an image from a IIIF image server. If you click on "HTML" you can see the URL that is being requested.

{% highlight html %}
<img src="https://stacks.stanford.edu/image/iiif/hg676jb4964%2F0380_796-44/1015,1460,799,824/pct:50/0/default.jpg">
{% endhighlight %}

This URL is crafted to extract a specific region, at a relative size, from the high quality original image. The original image is measured at 5426 x 3820 pixels and has a file size of 4.7MB. Having users download the entire file is inefficient and will likely provide a poor user experience. The IIIF Image API allows you to serve out derivative versions of these images in a standardized way, without having to generate derivates in advance.

## Zoomable Images
Several different libraries now exist to use the IIIF Image API to provide a "deep zoom" for the images. Below is an example of the [Leaflet-IIIF](https://github.com/mejackreed/Leaflet-IIIF) displaying the same image we looked at previously. Here you can see the entire image and zoom in with great detail. Using tiled zoom enables viewing of high resolution images without needing to download the full resolution images. 

<iframe 
  src="https://mejackreed.github.io/Leaflet-IIIF/examples/index.html?url=https://stacks.stanford.edu/image/iiif/hg676jb4964%2F0380_796-44/info.json"
  frameborder="0" width="100%" height="500px">
</iframe>

## How does all of this work?
The IIIF Image API server knows how to efficiently deliver these images to the viewer client. The viewer client knows what types of images that it can request from the server. The client gets this information from the server through a [Image Information](http://iiif.io/api/image/2.1/#image-information) request.

Let's dive into more of how the Image API works.

<div class='d-flex justify-content-around'>
  <a class="btn btn-secondary btn-lg" href="{{'image-api/playground' | relative_url }}">
    <span class='next-continue'>Continue :arrow_right:</span>
    <span class='next-title'>Image API Playground</span>
  </a>
</div>
