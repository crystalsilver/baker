# baker, the real static blog generator in bash

![baker](http://i.imgur.com/Tngl5Vv.png)

It is under a big redesign.

## Why

- simple: bring your own editor
- fun: use any command in your blog
- portable: blog on almost any linux/mac distribution

## Template redesigned

The new template engine is much faster (and smaller) than the previous version. It now uses bash's scope as its context.

### variable

Variable identifier should only use `[a-z_]`. Notice that any number is not allowed in a variable name.

```
{{ var_name }}

{{ yield }} # embed the current layout output to its parent
```

### if

Notice that spaces are not allowed between `!` and `var`.

```
@if !var
	...
@end
```

### for

```
@for element in array
	...
@end
```

### include

`@include` includes a partial from `$LAYOUT_DIR/$filename.md`. Notice that `.md` is already added.

```
@include filename
```

### cmd

`@cmd` uses any command's stdout and ignore its stderr. For example, `@cmd cal` will get a calendar.

```
@cmd ...
```

## Markdown

It currently uses the implementation from [Daring Fireball](http://daringfireball.net/projects/markdown/).

## License

This software is made by taylorchu, and is released under GPL2.
