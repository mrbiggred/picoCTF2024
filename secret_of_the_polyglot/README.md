Opening the file in Windows with at PDF extension gives the last part of the flag.

There is a PNG at the start of the PDF file.  I found it by trying to extract all the text from the PDF:

```
s -sDEVICE=txtwrite -o output.txt flag2of2-final.pdf

GPL Ghostscript 10.02.1 (2023-11-01)
Copyright (C) 2023 Artifex Software, Inc.  All rights reserved.
This software is supplied under the GNU AGPLv3 and comes with NO WARRANTY:
see the file COPYING for details.
   **** Warning: File has some garbage before %PDF- .
Processing pages 1 through 1.
Page 1
Loading font Helvetica (or substitute) from /usr/share/ghostscript/10.02.1/Resource/Font/NimbusSans-Regular

The following errors were encountered at least once while processing this file:
        startxref offset invalid
        xref table was repaired

The following warnings were encountered at least once while processing this file:
        File has some garbage before %PDF-

   **** This file had errors that were repaired or ignored.
   **** The file was produced by: 
   **** >>>> GPL Ghostscript 10.01.2 <<<<
   **** Please notify the author of the software that produced this
   **** file that it does not conform to Adobe's published PDF
   **** specification.

Error: finalizing subclassing device while child refcount > 1
```

You can use a hex editor, like [hexed](https://hexed.it/) to extract the PNG and get the start of the key.