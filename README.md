# react-resizable-and-movable

Resizable and movable component for React.

[![Build Status](https://travis-ci.org/bokuweb/react-resizable-and-movable.svg)](https://travis-ci.org/bokuweb/react-resizable-and-movable)
[![License](http://img.shields.io/npm/l/object.assign.svg)](https://github.com/bokuweb/react-resizable-box#license)

## Demo

![screenshot](https://raw.githubusercontent.com/bokuweb/react-resazable-and-movable/master/screenshot.gif)
See demo: [http://bokuweb.github.io/react-resazable-and-movable](http://bokuweb.github.io/react-resazable-and-movable)

## Important Note

This is an alpha release. Use with caution and hope.

## Installation

```sh
npm i react-resizable-and-movable
```

## Overview

### Basic

``` javascript
      <ResizableAndMovable
         width={200}
         height={200}
        <p>Example</p>
      </ResizableAndMovable>
```

### With min/max width/height and callbacks

``` javascript
      <ResizableAndMovable
         customStyle={{background:"#333", textAlign:"center", paddingTop: '20px'}}
         width={200}
         height={200}
         minWidth={200}
         minHeight={200}
         maxWidth={300}
         maxHeight={300}
         onResizeStart={() => console.log('resize start')}
         onResize={size => console.log(size)}
         onResizeStop={() => console.log('resize stop')}
         onDragStart={() => console.log('drag start')}
         onDrag={(e, ui) => {
           console.dir(ui);
           console.log(e);
         }}
         onDragStop={() => console.log('drag stop')} >
        <p>Example</p>
        <p>start 200px x 200px</p>
        <p>min 200px x 200px</p>
        <p>max 300px x 300px</p>
      </ResizableAndMovable>
```
## Properties

#### width {number}

The default width of the element.   

#### height {number}

The default height of the element.   

#### minWidth {number}

The minimum width of the element.

#### minHeight {number}

The minimum height of the element.

#### maxWidth {number}

The maximum width of the element.

#### maxHeight {number}

The maximum height of the element.

#### customClass {string}

The css class set on the element.

#### customStyle {object}

The css style set on the element.

#### onClick {func}

Callback called on element clicked.

#### onTouchStart {func}

Callback called on element touched.

#### onResizeStart {func}

Callback called on resize start.   

#### onResize {func}

Callback called on resizing.   
Receives the box size `{width: number, height: number}` as argument.

#### onResizeStop {func}

Callback called on resize stop.

#### onDrageStart {func}

Callback called on dragging start.   

#### onDrage {func}

Callback called on resizing.   
`onDrag` called with the following parameters:

``` javascript
(
 event: Event,
 ui:{
      node: Node
      position:
        {
            // lastX + deltaX === clientX
          deltaX: number, deltaY: number,
          lastX: number, lastY: number,
          clientX: number, clientY: number
        }
    }
)
```

#### onDrageStop {func}

Callback called on dragging stop.

## Test

``` sh
npm t
```

## License

The MIT License (MIT)

Copyright (c) 2016 @Bokuweb

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.