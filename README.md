# StyleLint Rules
SASS/CSS Guidelines

<div align="center">
  <a href="https://everymatrix.com/sass-standards.pdf">
    <img src="https://everymatrix.com/wp-content/themes/em2/img/redesign/logo-everymatrix.png" alt="EveryMatrix" />
  </a>
</div>
<br>
<p>
<a href="https://www.npmjs.org/package/stylelint"><img src="http://img.shields.io/npm/v/stylelint.svg" alt="NPM version"></a>
<a href="https://travis-ci.org/stylelint/stylelint"><img src="https://travis-ci.org/stylelint/stylelint.svg?branch=master" alt="Build Status"></a>
</p>

<br>

:tada: There are the rules for a fool proof CSS file

These rules will help you write better CSS/SCSS code for better Standards.

The rules are:

- do not use **empty class**  .foo { }
- do not use **multiple classes per line**  .foo { } .bar { }
- do not use **invalid color variables**  color: #y3;
- use simpler color **3 digit hex**  use #FFF instead of #FFFFFF for saving bits on the final file size.
- add space after property: { color:pink } { border:0; }
- do not define the same property multiple times .foo { color: pink; border: 0; color: orange;   }
- do not use properties which are ignored
    - .fa { display: inline; width: 100px; }
    - .fb { display: inline-block; float: left; }
    - .fc { display: block; vertical-align: baseline; }
- do not ever use !important .foo { color: #000 !important; }
- do not use properties which are overwriten:
    - .ga { padding-left: 10px; padding: 20px; }
    - .gb { transition-property: opacity; transition: opacity 1s linear; }
    - .gc { border-top-width: 1px;  border: 2px solid blue; }
- do not use nesting with more than 3 descendents:
.i {
    span {
        div { color: pink;
            a { display: none; }
        }
    }
}
- do not use duplicate selectors: .foo { height: auto; } .bar { } .foo { }
- do not use units with 0
    - .aj { top: 0px; }
    - .ak { height: 0.000em; }

- do not use px for font-size, use em, vh .foo { font-size: 12px; }

- do not use id selectors #foo { height: auto; }

- do not forget quotes on font-family .foo { font-family: Times New Roman, Times, serif; }

- do not use numbers on font-weight .foo { font: italic 400 20px; font-weight: 700; }

- do not use Uppercase in properties .foo { Width: 1px }

- do not use universal selector * { margin: 0; }

- do not use more than 3 compound selectors
    .foo .bar .baz .lorem { height: auto; }
    .foo .baz {
      & > .bar .lorem { color: pink; }
    }
    .foo + div:not(.a ~ .c) { color: white; } /* strangely this is not an error --> .a ~ .c is inside :not() and is processed separately */

- do not use multi-lines values when declaring values with comma
    a { background-size: 0
      , 0; }



## Features
