<amplify-block-switcher>
<amplify-block name="Vue 3">

```js
import { createApp } from 'vue';
import App from './App.vue';
import { 
  applyPolyfills,
  defineCustomElements
} from '@aws-amplify/ui-components/loader';

import Amplify from 'aws-amplify';
import awsconfig from './aws-exports';
Amplify.configure(awsconfig);

applyPolyfills().then(() => {
  defineCustomElements(window);
});

const app = createApp(App);
app.config.isCustomElement = tag => tag.startsWith('amplify-');
app.mount('#app');
```

<amplify-callout warning>

If you are using the runtime-only build, you must configure `isCustomElement` from the compiler configuration. You can use <amplify-external-link href="https://gist.github.com/wlee221/3d47f9598d5ad85bfa7a138bad112c3c"><code>vue.config.js</code></amplify-external-link> gist or <amplify-external-link href="https://gist.github.com/wlee221/3d47f9598d5ad85bfa7a138bad112c3c"><code>vite.config.js</code></amplify-external-link> gist to configure them for example. 

</amplify-callout>

</amplify-block>
<amplify-block name="Vue 2">

```js
import Vue from "vue";
import App from "./App.vue";
import "@aws-amplify/ui-vue";
import Amplify from "aws-amplify";
import awsconfig from "./aws-exports";

Amplify.configure(awsconfig);

new Vue({
  render: (h) => h(App),
}).$mount("#app");
```

</amplify-block>
</amplify-block-switcher>