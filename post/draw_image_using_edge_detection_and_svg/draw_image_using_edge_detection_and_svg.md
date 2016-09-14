## [轉載] Drawing images using edge detection and SVG animation [Back](./../post.md)

> - Author: [José M. Pérez](https://jmperezperez.com/about-me/)
- Origin: https://jmperezperez.com/drawing-edges-svg/
- Time: Dec, 18th, 2015

Back in the days SVG was barely used and supported. Some time after we started using them as an alternative to classic bitmaps for some icons, and finally we discovered it was the holy grail for providing responsive graphics. The flat and clean design trends have also make SVG as a very useful image format.

But SVG allows for even cooler features, thanks to the ability of modifying it using CSS and JS. And with some clever techniques we can make fun things, like drawing the borders of an image.

If you are like me and like to see the final result before going through a wall of text, here is a video that shows the result of applying this effect to a couple of images:

Video Source: https://jmperezperez.com/assets/images/posts/contour.mp4

<video controls="" style="max-width:100%">
  <source src="https://jmperezperez.com/assets/images/posts/contour.mp4" type="video/mp4">
</video>

### Animate SVGs to achieve a ***drawing*** effect

One of the applications I like is path animation. This draws slowly the lines that compose the SVG. If you don’t know what this is about, please check [Polygon's reviews for PS4](http://www.polygon.com/a/ps4-review) and [Xbox One](http://www.polygon.com/a/xbox-one-review). The effect is achieved by applying transitions to the stroke-dashoffset of SVG polylines.

Some time ago I played with this technique and the vector version of the Spotify logo: