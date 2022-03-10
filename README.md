PDFGen for RT-Thread
======
<img src="/pdfgen_logo.png" alt="PDFGen Logo" width="200" align="right"/>

Simple C PDF Creation/Generation library.
All contained a single C-file with header and no external library dependencies.

Useful for embedding into other programs that require rudimentary PDF output.

Supports the following PDF features
* Text of various fonts/sizes/colours
* Primitive drawing elements
    * Lines
    * Rectangles
    * Filled Rectangles
    * Polygons
    * Filled Polygons
    * Bezier curves
* Bookmarks
* Barcodes (Code-128 & Code-39)
* Embedded images
    * PPM/PGM (binary format only)
    * JPEG
    * PNG (Alpha Channels are not supported)
    * BMP

Example usage
=============
```c
#include "pdfgen.h"

int main(void) {
    struct pdf_info info = {
        .creator = "My software",
        .producer = "My software",
        .title = "My document",
        .author = "My name",
        .subject = "My subject",
        .date = "Today"
    };
    struct pdf_doc *pdf = pdf_create(PDF_A4_WIDTH, PDF_A4_HEIGHT, &info);
    pdf_set_font(pdf, "Times-Roman");
    pdf_append_page(pdf);
    pdf_add_text(pdf, NULL, "This is text", 12, 50, 20, PDF_BLACK);
    pdf_add_line(pdf, NULL, 50, 24, 150, 24, 3, PDF_BLACK);
    pdf_save(pdf, "output.pdf");
    pdf_destroy(pdf);
    return 0;
}
```

License
=======
[![License: Unlicense](https://img.shields.io/badge/license-Unlicense-blue.svg)](http://unlicense.org/)

The source here is public domain.
If you find it useful, please drop me a line at andre@ignavus.net.


# 如何打开 PDFGen

使用 PDFGen 需要在 RT-Thread 的包管理器中选择它，具体路径如下：

```
RT-Thread online packages
    multimedia packages --->
        [*] PDFGen: Simple C PDF Writer/Generation library  --->
```


# 维护 & 联系

主页：https://github.com/mysterywolf/PDFGen

维护：[Meco Man](https://github.com/mysterywolf)
