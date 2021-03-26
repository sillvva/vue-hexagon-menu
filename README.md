# vue-hexagon-menu

## Demo

I've created a few variations of this menu here:

https://www.mattdekok.dev/

----

## Example Usage

```javascript
import HexMenu from "../components/hex-menu.vue";

export default {
  components: {
    HexMenu,
  },
  data() {
    return {
      items: [
        { link: "/about", label: "About Me" },
        { link: "/experience", label: "Experience" },
        { link: "/skills", label: "Skills" },
        { link: "/projects", label: "Projects" },
        { link: "/donate", label: "Donate" },
      ],
    };
  },
};
```

![img](https://i.imgur.com/o4onSyp.png?1)

```html
<hex-menu
  :maxLength="3"
  :items="items"
  color="#6c6"
  hoverColor="#69c"
></hex-menu>
```

![img](https://i.imgur.com/XGK4ACj.png?1)

```html
<hex-menu
  :items="items"
  rotated
  color="#6c6"
  hoverColor="#69c"
></hex-menu>
```

----
# Documentation

## Menu Properties

| Property | Required? | Default | Description |
| :- | :-: | :-: | :- |
| items | Y | | Must be an array of objects. For a list of properties, see the following section. |
| maxLength | N | `0` | The maximum number of items in any row of the menu. If `rotated` is false, then every even row will have a max length of 1 less than this property. |
| rotated | N | `false` | If true, the flat side will be on the top/bottom sides of the hexagon. If false, the flat side will be on the left/right sides. See the examples above. |
| color | N | `#6c6` | Sets the default color for all menu items. |
| activeColor | N | `#69c` | Sets the default active color for all menu items. |
| hoverColor | N | `#69c` | Sets the default hover color for all menu items. |
| textColor | N | `#fff` | Sets the default text color for all menu items. |
| wrapperClasses | N | `[]` | An array of CSS class names to add to the menu wrapper element. |
| svgClasses | N | `[]` | An array of CSS class names to add to each menu item's svg element. |
| hexagonClasses | N | `[]` | An array of CSS class names to add to each menu item's hexagon shape. |
| textClasses | N | `[]` | An array of CSS class names to add to each menu item's text. |

## Item Properties

Each item must be an object with the following properties.

| Property | Required? | Default | Description |
| :- | :-: | :-: | :- |
| link | Y | | A url for the menu item. Not required if the `empty` property is true. |
| label | Y | | A label for the menu item. Not required if the `empty` property is true. |
| empty | N | `false` | Skips a slot on the menu. See the example below. |
| active | N | `false` | Gives the menu item the active color. |
| color | N | `#6c6` | Sets the color of the menu item. |
| activeColor | N | `#69c` | Sets the color while the menu item is active. |
| hoverColor | N | `#69c` | Sets the color while the cursor is hovering over the menu item. |
| textColor | N | `#fff` | Sets the text color for the menu item. |
| svgClasses | N | `[]` | Sets the text color for the menu item's svg element. |
| hexagonClasses | N | `[]` | Sets the text color for the menu item's hexagon shape. |
| textClasses | N | `[]` | Sets the text color for the menu item's text. |

## Empty Item

Adding an empty item allows you to skip menu slots, like this:

![img](https://i.imgur.com/3D4zv0N.png?2)

```html
<hex-menu
  :maxLength="3"
  :items="items"
  rotated
></hex-menu>
```

```javascript
import HexMenu from "../components/hex-menu.vue";

export default {
  components: {
    HexMenu,
  },
  data() {
    return {
      items: [
        { link: "/about", label: "About Me" },
        { link: "/experience", label: "Experience" },
        { link: "/skills", label: "Skills" },
        { link: "/projects", label: "Projects" },
        { empty: true },
        { link: "/donate", label: "Donate" },
      ],
    };
  },
};
```

## Animating menu items

Since you can pass classes to the menu items, you can add animations to them on `:hover`.

```html
<hex-menu
  :maxLength="3"
  :items="items"
  :svgClasses="['menu-shake']"
  rotated
></hex-menu>
```

The animations style should be placed in a non-scoped style block.

```html
<style lang="scss">
.menu-shake:hover:not(.active):not(.empty) {
  animation: shake 500ms ease-in-out forwards;
}
@keyframes shake {
  40% {
    transform: scale(1.5);
  }
  60% {
    transform: rotate(-5deg);
  }
  80% {
    transform: rotate(5deg);
  }
  100% {
    transform: rotate(0deg);
  }
}
</style>
```