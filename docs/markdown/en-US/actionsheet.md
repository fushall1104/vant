## Actionsheet

### Install
``` javascript
import { Actionsheet } from 'vant';

Vue.use(Actionsheet);
```

### Usage

#### Basic Usage
Use `actions` prop to set options of actionsheet. 

```html
<van-actionsheet v-model="show" :actions="actions" />
```

```javascript
export default {
  data() {
    return {
      show: false,
      actions: [
        { name: 'Option1', callback: this.onClick },
        { name: 'Option2' },
        { name: 'Option3', loading: true }
      ]
    };
  },

  methods: {
    onClick(item) {
      Toast(item.name);
    }
  }
}
```

#### Actionsheet with cancel button

```html
<van-actionsheet v-model="show" :actions="actions" cancel-text="Cancel" />
```

#### Actionsheet with title
Actionsheet will get another style if there is a `title` prop.

```html
<van-actionsheet v-model="show" title="Title">
  <p>Content</p>
</van-actionsheet>
```

### API

| Attribute | Description | Type | Default | Accepted Values |
|-----------|-----------|-----------|-------------|-------------|
| actions | Options | `Array` | `[]` | - |
| title | Title | `String` | - | - |
| cancel-text | Text of cancel button | `String` | - | - |
| overlay | Whether to show overlay | `Boolean` | - | - |
| close-on-click-overlay | Whether to close when click overlay | `Boolean` | - | - |
| get-container | Return the mount node for actionsheet | `Function` | - | `() => HTMLElement` |

### Data struct of actions

| key | Description |
|-----------|-----------|
| name | Title |
| subname | Subtitle |
| className | className for the option |
| loading | Whether to be loading status |
| callback | Triggered when click option |
