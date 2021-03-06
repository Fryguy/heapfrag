# Heapfrag

* https://github.com/tenderlove/heapfrag

## DESCRIPTION:

This is a library for dumping and visualizing your heap in MRI.  This code is
not for the feint of heart.  I don't know what versions of Ruby this will work
on, and I make no guarantees about which versions I support or anything.  If
it doesn't work for you, please send a PR!

This. Is. A. Huge. Hack.

## FEATURES/PROBLEMS:

* All of them

One problem is that the heap dumped as JSON is really big.  I'm having
problems dumping it fast enough.  You can adjust the timer interval when you
call `Heapfrag.start`, so if you have a large heap, then a slower interval
might be better.

## SYNOPSIS:

In one terminal:

```
$ ruby bin/heap2raster.rb /tmp/sock
```

In a different terminal:

```
$ ruby --disable-gem -Ilib -rsocket -rheapfrag -S irb
irb(main):001:0> Heapfrag.start(500_000, UNIXSocket.open("/tmp/sock"))
=> true
irb(main):002:0> GC.start
=> nil
irb(main):003:0> x = 5000.times.map { Object.new }; nil
=> nil
```

Hopefully this gif will help:

![demo](demo.gif)

## REQUIREMENTS:

* opengl
* glu
* glut

## INSTALL:

You should use this from Git.

## LICENSE:

(The MIT License)

Copyright (c) 2016 Aaron Patterson

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
