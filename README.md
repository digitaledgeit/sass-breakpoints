# sass-breakpoints

SASS mixins for named breakpoints.

- Named breakpoints improve readability and maintainability
- Customisable breakpoints allow you to target whatever devices you want
- Breakpoints are set in `em` and scale with the user's base font-size

## Installation

    npm install --save sass-breakpoints

## Usage

    $ sass-composer example/example.scss -o compiled.css

SCSS: `example/settings.scss`

    //these are the default settings if not specified by the user
    $breakpoints: (
      "xs": 0px,    //targeting <568px devices (e.g. all iPhones <6)
      "sm": 568px,  //targeting >=568px devices (e.g. iPhones >=6)
      "md": 768px,  //targeting >=768px tablets (e.g. portrait iPad)
      "lg": 1004px  //targeting >=1024px tablets (e.g. landscape iPad) and desktops but leaving room for the scroll bar
    );

SCSS: `example/example.scss`

    @import "./settings";
    @import "sass-breakpoint";
    
    @include breakpoint('sm') {           //from `sm` (>=0px)
      body {
        background-color: red;
      }
    }
    
    @include breakpoint('md', 'lg') {     //from `md` to `lg - 1px` (>=768px to <1024px)
      body {
        background-color: green;
      }
    }
    
    @include breakpoint('lg') {           //from `lg` (>=1024px)
      body {
        background-color: blue;
      }
    }
    
CSS: `compiled.scss`
        
    @media (min-width: 35.5em) {
      body {
        background-color: red; } }
    
    @media (min-width: 48em) and (max-width: 62.6875em) {
      body {
        background-color: green; } }
    
    @media (min-width: 62.75em) {
      body {
        background-color: blue; } }

## API
    
### breakpoint($from, $to: null)

    @include breakpoint('xs') {           //>=0px
      body { color: red; }
    }
    
    @include breakpoint('sm, 'md') {      //>=568px but <768px
      body { color: blue; }
    }
 
### breakpoint-lt($to)

    @include breakpoint-lt('md') {        //<768px
      body { color: red; }
    }

### breakpoint-lte($to)

    @include breakpoint-lte('md') {       //<=768px
      body { color: red; }
    }

### breakpoint-gt($from)

    @include breakpoint-gt('md') {        //>768px
      body { color: red; }
    }

### breakpoint-lte($to)

    @include breakpoint-gte('md') {       //>=768px
      body { color: red; }
    }

### breakpoint-between($from, $to)
    
    @include breakpoint-between('sm', 'md') { //>568px but <768px
      body { color: red; }
    }

## License

The MIT License (MIT)

Copyright (c) 2015 James Newell