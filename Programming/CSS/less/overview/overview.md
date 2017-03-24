## Overview [Back](./../less.md)

### Variables

```less
@nice-blue: #5B83AD;
@light-blue: @nice-blue + #111;

#header {
    color: @light-blue;
}
```

```css
#header {
    color: #6c94be;
}
```

***Note that variables are actually "constants" in that they can only be defined once.***

### Mixins

Mixins are a way of including a bunch of properties from one rule-set into another rule-set.

```less
.bordered {
    border-top: dotted 1px black;
    border-bottom: solid 2px black;
}

#id {
    border: solid 1px black;
}
```

```less
#menu a {
    color: #111;
    .bordered;
}

.post a {
    color: red;
    .bordered;
    #id;
}
```

### Nested Rules

Less gives you the ability to use nesting instead of, or in combination with cascading.

Like the following CSS:

```css
#header {
    color: black;
}
#header .navigation {
    font-size: 12px;
}
#header .logo {
    width: 300px;
}
```

We can code it with Less:

```less
#header {
    color: black;
    .navigation {
        font-size: 12px;
    }
    .logo {
        width: 30px;
    }
}
```

When bundling pseudo-selectors, you can use `&` to reference the current selector parent:

Like the following CSS:

```css
.clearfix {
    display: block;
    zoom: 1;
}

.clearfix:after {
    content: " ";
    display: block;
    font-size: 0;
    height: 0;
    clear: both;
    visibility: hidden;
}
```

We can code it with Less:

```less
.clearfix {
    display: block;
    zoom: 1;
    &:after {
        content: " ";
        display: block;
        font-size: 0;
        height: 0;
        clear: both;
        visibility: hidden;
    }
}
```

When it comes to directives like `@media` or `@keyframe`, we can also use this rule to nest them:

Like the following CSS:

```css
@media screen {
    .item {
        color: green;
    }
}

@media screen and (min-width: 768px) {
    .item {
        color: red;
    }
}

@media tv {
    .item {
        color: black;
    }
}
```

We can code it with Less:

```less
.item {
    @media screen {
        color: green;
        
        @media (min-width: 768px) {
            color: red;
        }
    }
    
    @media tv {
        color: black;
    }
}
```

Remaining non-conditional directives, for example `@font-face` or `@keyframes`, are bubbled up too. Their bodies do not change:

```less

#a {
    color: blue;
    @font-face {
        src: made-up-url;
    }
    padding: 2;
}
```