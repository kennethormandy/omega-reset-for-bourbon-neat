# Omega Reset for Bourbon Neat

## Bourbon Neat's Grid Settings

Create a `_grid-settings.scss` file. Bourbon Neat looks for that file to see if there are any overrides to their built in settings. You can read more about it in the [Bourbon docs](http://bourbon.io/docs/#flex-grid).

    $fg-column: $column;
    $fg-gutter: $gutter;

[http://joshfry.me/notes/omega-reset-for-bourbon-neat/#update-your-grid-settings](http://joshfry.me/notes/omega-reset-for-bourbon-neat/#update-your-grid-settings)


## Omega Reset Mixin

Create a `_mixins.scss` file. This is the omega-reset mixin:

    @mixin omega-reset($nth) {
      &:nth-child(#{$nth}) { margin-right: flex-gutter(); }
      &:nth-child(#{$nth}+1) { clear: none }
    }

[http://joshfry.me/notes/omega-reset-for-bourbon-neat/#include-omega-reset-mixin](http://joshfry.me/notes/omega-reset-for-bourbon-neat/#include-omega-reset-mixin)

## Useage

    @include breakpoint(480px)  {
      @include span-columns(6);
      @include omega(2n);
    }
    @include breakpoint(768px)  {
      @include omega-reset(2n); // Pass in the previous media query's omega() argument to reset it
      @include span-columns(4);
      @include omega(3n);
    }

[http://joshfry.me/notes/omega-reset-for-bourbon-neat/#how-to-use-omega-reset-in-your-html](http://joshfry.me/notes/omega-reset-for-bourbon-neat/#how-to-use-omega-reset-in-your-html)
