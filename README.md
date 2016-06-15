# StyleLint Rules
SASS/CSS Coding Standards

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

:tada: Here are the rules for a foolproof CSS file

These rules will help you write better CSS/SCSS code for better Standards.

<img src="https://raw.githubusercontent.com/AtomLinter/linter-stylelint/master/demo.png" alt="demo" />

The rules are:

- do not use empty class  .foo { }
- do not use multiple classes per line  .foo { } .bar { }
- do not use invalid color variables  color: #y3;
- use simpler color 3 digit hex  use #FFF instead of #FFFFFF for saving bits on the final file size.
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
- do not use duplicate selectors .foo { height: auto; } .bar { } .foo { }
- do not use units with 0 .aj { top: 0px; } .ak { height: 0.000em; }
- do not use px for font-size, use em, vh .foo { font-size: 12px; }
- do not use id selectors #foo { height: auto; }
- do not forget quotes on font-family .foo { font-family: Times New Roman, Times, serif; }
- do not use numbers on font-weight .foo { font: italic 400 20px; font-weight: 700; }
- do not use Uppercase in properties .foo { Width: 1px }
- do not use universal selector * { margin: 0; }
- do not use more than 3 compound selectors
    - .foo .bar .baz .lorem { height: auto; }
    - .foo .baz {
        & > .bar .lorem { color: pink; }
        }
    - .foo + div:not(.a ~ .c) { color: white; } /* strangely this is not an error --> .a ~ .c is inside :not() and is processed separately */
- do not use multi-lines values when declaring values with comma:
    a { background-size: 0
      , 0; }



## Features
- **Supports all CSS syntax:** Including custom properties, range context for media features, `calc()` and nesting.
- **Understands CSS-like syntaxes:** it understands any CSS syntax including SCSS.
- **Works only with stylelint:** [stylelint](http://stylelint.io/) is a mighty, modern CSS linter. stylefmt can understand the formatting rules specified in your stylelint configuration file (`.stylelintrc`).
- **Works with linter-stylelint** [linter-stylelint](https://atom.io/packages/linter-stylelint) A plugin for Atom Linter providing an interface to stylelint.
- **The rules** are based on the EveryMatrix Coding Standards and the full list can be seen [here](http://stylelint.io/user-guide/rules/)

- **Uses a properties order**:
    1. BOX & STATUS MODIFIERS (display, visibility, opacity, float, clear, content, list-style*, marker-offset, box-*, grid-*, zoom, etc),
    2. SIZE & ARRANGEMENT (width, height, max-/min-*, margin*, padding*, position, top/right/bottom/left, clip, z-index, etc),
    3. COLOR & BG (background*, color*, border*, outline*),
    4. TEXT (font*, line-*, text-*, word-*, letter-*, white-space*, column-*, etc),
    5. SPECIAL EFFECTS (animation*, transition*, transform*, perspective*, *-shadow, border-radius)
    6. OTHERS (cue*, speak*, mark*, rest*, voice*, ruby*, fit*, page*, appearance, cursor, nav-*, etc)


## Instalation
- Install **stylelint:** [stylelint](http://stylelint.io/)
- Install **linter-stylelint** [plugin](https://github.com/AtomLinter/atom-linter) for Atom Linter to provide a interface to <a href="https://github.com/stylelint/stylelint">stylelint</a>.
<pre class="editor">
        <span>apm&nbsp;install&nbsp;linter-stylelint</span>  
</pre>
