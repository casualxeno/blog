---
layout: post
title:  "The easiest way to create an image"
categories: [coding]
author: "xeno"
---

The simplest format to create graphics is [PBM][pbm]. It's very straightforward and supports ASCII, making it very easy to write a program that produces an image.

You can further simplify this by using standard print functions to redirect the output to a file.

Here's a simple code snippet that generates an image:
```py
WIDTH = 800
HEIGHT = 800

if __name__ == '__main__':
  print('P3')
  print(f'{WIDTH} {HEIGHT}')
  print(255)
  for y in range(HEIGHT):
    for x in range(WIDTH):
      for _ in range(3):
        print((x + y) % 255, end=' ')
      print()
```

```sh
python3 ./main.py > ./out.ppm
open ./out.ppm
```

![out.ppm](assets/img/posts/2026-07-09-easiest-way-to-create-image/out.jpg)

***

You can easily apply color interpolation:

![gradient.ppm](assets/img/posts/2026-07-09-easiest-way-to-create-image/gradient.jpg)

And build a ray tracer:

![raytracer.ppm](assets/img/posts/2026-07-09-easiest-way-to-create-image/raytracer.jpg)

While utilizing GPU and shaders will significantly improve the performance, you can quickly prototype your ideas using the CPU.

[pbm]: https://en.wikipedia.org/wiki/Netpbm