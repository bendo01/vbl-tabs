## Installation

```console
$ npm install vbl-tabs --save
```

## Examples

```vue
<template>
    <tabs>
        <tab name="About Us" :selected="true">
            <h1>Here is the content for the about us tab.</h1>
        </tab>
        <tab name="About Our Culture">
            <h1>Here is the content for the about our culture tab.</h1>
        </tab>
        <tab name="About Our Vision">
            <h1>Here is the content for the about our vision tab.</h1>
        </tab>
    </tabs>
</template>

<script>
'use strict';
import { Tabs, Tab } from 'vbl-tabs';
export default {
    components: {
        Tabs,
        Tab
    }
}
</script>
```
