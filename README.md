# sass-simple-animate
An easy way to write css animation.<br>
Is it quite often writing @keyframes for just one animation of certain selector? Are they hard to manage?<br>
*sass-simple-animate* give you a friendly approach to write such animations. Let's take a look:

###example
```scss
@import "scss/animate"; //import the mixin
div {
    @include animate(5s linear infinite) {
        from { background-color: red; }
    	to   { background-color: green; }
    }
}
```
will be compiled to:
```css
div {
	-webkit-animation: ssa-u8a16c123 10s infinite;
	-moz-animation: ssa-u8a16c123 10s infinite;
	animation: ssa-u8a16c123 10s infinite;
}
@-webkit-keyframes(ssa-u8a16c123) {
	from { background-color: red; }
	to   { background-color: green; }
}
@-moz-keyframes(ssa-u8a16c123) {
	from { background-color: red; }
	to   { background-color: green; }
}
@keyframes(ssa-u8a16c123) {
	from { background-color: red; }
	to   { background-color: green; }
}
```

###usage
```scss
//selector can be nested
<selector> {
    //paramters are same as CSS animation's porperty values
    //except that NO animation-name here (it will be auto generated)
    @include animate([duration] [timing-function] [delay] [iteration-count] [direction] [fill-mode] [play-state]) {
        [keyframes content] //the content of keyframes
        }
}
```

###installation
Copy all files under /scss folder into your project or repository, and use it with other sass and scss code.

###pre-requirement
libsass 3.2.5+, or use the last version of Sass will be fine.