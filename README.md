# get-bem

A sass library from easily generating BEM methodology style classes


## Usage
Import it into your main stylesheet:

````scss
@import 'get-bem.scss';
````


## Example
````scss
@import 'get-bem.scss';
 
@include block("content") {
    width: 100%;

    @include modifier('hidden') {
        visibility: hidden;
    }

    @include element('body') { 
        display: flex;
        justify-content: center;
        font-size: 1.1rem;

        @include modifier('small') {
            font-size: 1rem;
        }

        @include modifier('tiny') {
            font-size: .75rem;
        }

        @include element('image') { 
            width: 200px;
            height: 200px;
        }
    }

    @include element('footer') {
        border-top: 1px solid initial;
    }
}
````

The compiled CSS:

````css
.content {
  width: 100%;
}
.content--hidden {
  visibility: hidden;
}
.content__body {
  display: flex;
  justify-content: center;
  font-size: 1.1rem;
}
.content__body--small {
  font-size: 1rem;
}
.content__body--tiny {
  font-size: 0.75rem;
}
.content__body__image {
  width: 200px;
  height: 200px;
}
.content__footer {
  border-top: 1px solid initial;
}

````

### Configs

By default BEM Constructor uses the following BEM convention:
- Two underscores (__) for elements
- Two hyphens for modifiers (--).

You can customize them:
````scss
    $element-seperator: '_E_'; // Defaults to '__'

    $modifier-seperator: '-M-'; // Defaults to '--'
````

### What the BEM?
BEM (Block, Element, Modifier) is a naming convention methodology that makes your css reusable understandable, easier, scalable.

[More info](http://getbem.com/)
