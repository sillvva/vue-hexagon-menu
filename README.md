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
  :classes="['home-styles']"
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
