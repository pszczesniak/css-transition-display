# css-transition-display -  Fix for transitions to work with display property.

It's quite easy to use. It's based on css animations.

## Quick start
### 1. Simple hover.
We need to define animation keyframes:
```css
@keyframes test-animation {
  0% {
    display: none;
    opacity: 0;
    visibility: hidden;
  }

  1% {
    display: block;
    opacity: 0;
    visibility: hidden;
    transform: translateY(50vh);
  }

  100% {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
  }
}
```
As you can see, on the beginning of animation there is `display:none;` - there we can set base state of animated element. On next keyframe we change from `none` to `block`. And... that is it :) Now on next keyframes you can set what you want, so this element will behave like You want:)

[Here](https://github.com/pszczesniak/css-transition-display/blob/master/transition-over.html) is fully working example of this solution.

### 2. More complex hover action.
You can use it to set states on hover and when hover is out. I will show below the easiest way, but this solution can behave differently in your case.

We need to define animation keyframes for over and out states. Then we need to add animation-out on element and animation-over when element is hovered. `display:block` and `display: hidden` is used only in keyframes. To create fake `display:none` we can use `position: absolute` and play with `z-index`.

[Here](https://github.com/pszczesniak/css-transition-display/blob/master/transition-over-out.html) is fully working example of this solution.
