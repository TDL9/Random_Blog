# Typed Racket 简单光线追踪

参考
https://github.com/RayTracing/raytracing.github.io
https://in1weekend.blogspot.com/
实现一个简单的光线追踪渲染，使用 typed/racket 实现，纯属出于个人兴趣。

我曾经上过一门图形学课程，但是没有好好珍惜。

## PPM
使用 PPM 格式是最直观的输出图像的方式：
![](https://raytracing.github.io/images/fig-1.01-ppm.jpg)

## 开始
```rkt
#lang typed/racket

(require math/matrix)
(define image-width 512)
(define image-height 288)

(: main (Output-Port -> Any))
(define (main f)
  (fprintf f "P3\n")
  (fprintf f "256 256\n")
  (fprintf f "255\n")
  (for* ([i : Integer (in-range 256)]
         [j : Integer (in-range 256)])
    (fprintf f "~a ~a ~a\n" i j 255)))

(call-with-output-file "res.ppm" main #:exists 'replace)
```
