---
title: Custom Context Menu example
permalink: /next/vue-custom-context-menu-example
canonicalUrl: /vue-custom-context-menu-example
---

# Custom Context Menu example

An implementation of the `@handsontable/vue` component with a custom Context Menu added.

::: example #example1 :vue --html 1 --js 2
```html
<div id="example1">
  <hot-table :settings="hotSettings"></hot-table>
</div>
```
```js
import Vue from 'vue';
import { HotTable } from '@handsontable/vue';
import Handsontable from 'handsontable';

new Vue({
  el: '#example1',
  data() {
    return {
      hotSettings: {
        data: Handsontable.helper.createSpreadsheetData(5, 5),
        colHeaders: true,
        contextMenu: {
          items: {
            'row_above': {
              name: 'Insert row above this one (custom name)'
            },
            'row_below': {},
            'separator': Handsontable.plugins.ContextMenu.SEPARATOR,
            'clear_custom': {
              name: 'Clear all cells (custom)',
              callback() {
                this.clear();
              }
            }
          }
        },
        licenseKey: 'non-commercial-and-evaluation'
      }
    }
  },
  components: {
    HotTable
  }
});
```
:::
