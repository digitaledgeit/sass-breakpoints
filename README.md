# css-breakpoints

Mixins for creating breakpoints.

Features:

- breakpoints are set in `em`s and scale with the user's base font-size
- configurable named breakpoints

## Installation

  npm install --save digitaledgeit-breakpoints

## Usage

`example.scss`

    @import "digitaledgeit-breakpoints";
    
    @include named_breakpoint('xs') {
      body {
        background-color: red;
      }
    }
    
    @include named_breakpoint('md') {
      body {
        background-color: green;
      }
    }
    
`example.css`

    /* targeting devices from 0px */
    @media (min-width: 0em) {
      body {
        background-color: red; }
     }
    
    /* targeting devices from 768px */
    @media (min-width: 48em) {
      body {
        background-color: green; }
     }
     
    $ sassc example/example.scss

## License

The MIT License (MIT)

Copyright (c) 2014 James Newell

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.