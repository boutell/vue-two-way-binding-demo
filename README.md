# two-way-binding-1

A simple demonstration of two-way `v-model` data binding with a custom
Vue component, similar to what you can do out of the box
with input elements.

## One-time setup

```
npm install
```

### Start it up

```
npm run serve
```

### Now access the app

[http://localhost:8080](http://localhost:8080)

### What am I looking at?

**The text field at the top is two-way bound to the application.** As you type, the text is replicated below in a `p` tag. And if you click the "clear" button, both the text field and the `p` tag clear, because the binding works in both directions. This is done with Vue's [v-model directive](https://vuejs.org/v2/guide/forms.html), so we do not have to write any code to respond to `change` events on the text field. It just works.

**The color picker at the bottom is also two-way bound to the application.** As you pull the sliders, the previewed color changes, and you can also see the hex color displayed in a paragraph tag below, **outside the Color component itself**. And if you click "Reset Color," the color picker and the paragraph tag both revert to the original color, because the binding is two-way.

**The `Color.vue` component implements support for `v-model` even though it is not a standard form component.** To do that, we have to do two things:

1. *Accept our current value as a `prop` called `value`.* You don't see this prop being passed in because `v-model` does it for us.

2. *Every time the value should change, emit an `input` event with the new value.* The main `App.vue` component then gives it back to us as a prop, so our sliders and the color preview box update automatically.

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

