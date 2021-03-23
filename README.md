# vue-hexagon-menu

## Usage

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

## Menu Properties

| Property | Required? | Default | Description |
| :- | :-: | :-: | :- |
| items | Y | | Must be an array of objects. For a list of properties, see the following section. |
| maxLength | N | 0 | The maximum number of items in any row of the menu. If `rotated` is false, then every even row will have a max length of 1 less than this property. |
| rotated | N | false | If true, the flat side will be on the top/bottom sides of the hexagon. If false, the flat side will be on the left/right sides. See the examples above. |
| color | N | #6c6 | Sets the default color for all menu items. |
| activeColor | N | #69c | Sets the default active color for all menu items. |
| hoverColor | N | #69c | Sets the default hover color for all menu items. |
| textColor | N | #fff | Sets the default text color for all menu items. |
| classes | N | `[]` | An array of CSS class names to add to the menu wrapper element. |
| itemClasses | N | `[]` | An array of CSS class names to add to each menu item. |

## Item Properties

Each item must be an object with the following properties.

| Property | Required? | Default | Description |
| :- | :-: | :-: | :- |
| link | Y | | A url for the menu item. Not required if the `empty` property is true. |
| label | Y | | A label for the menu item. Not required if the `empty` property is true. |
| empty | N | false | Skips a slot on the menu. See the example above. |
| active | N | false | Gives the menu item the active color. |
| color | N | #6c6 | Sets the color of the menu item. |
| activeColor | N | #69c | Sets the color while the menu item is active. |
| hoverColor | N | #69c | Sets the color while the cursor is hovering over the menu item. |
| textColor | N | #fff | Sets the text color for each menu item. |