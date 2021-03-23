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
