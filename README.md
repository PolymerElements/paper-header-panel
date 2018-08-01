[![Published on NPM](https://img.shields.io/npm/v/@polymer/paper-header-panel.svg)](https://www.npmjs.com/package/@polymer/paper-header-panel)
[![Build status](https://travis-ci.org/PolymerElements/paper-header-panel.svg?branch=master)](https://travis-ci.org/PolymerElements/paper-header-panel)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://webcomponents.org/element/@polymer/paper-header-panel)

## &lt;paper-header-panel&gt;

**This element has been deprecated in favor of [app-layout](https://github.com/PolymerElements/app-layout).**

`paper-header-panel` contains a header section and a content panel section.

__Important:__ The `paper-header-panel` will not display if its parent does not have a height.

### Modes

Controls header and scrolling behavior. Options are `standard`, `seamed`, `waterfall`, `waterfall-tall`, `scroll` and
`cover`. Default is `standard`.

Mode | Description
----------------|-------------
`standard` | The header is a step above the panel. The header will consume the panel at the point of entry, preventing it from passing through to the opposite side.
`seamed` | The header is presented as seamed with the panel.
`waterfall` | Similar to standard mode, but header is initially presented as seamed with panel, but then separates to form the step.
`waterfall-tall` | The header is initially taller (`tall` class is added to the header). As the user scrolls, the header separates (forming an edge) while condensing (`tall` class is removed from the header).
`scroll` | The header keeps its seam with the panel, and is pushed off screen.
`cover` | The panel covers the whole `paper-header-panel` including the header. This allows user to style the panel in such a way that the panel is partially covering the header.

### Styling

To change the shadow that shows up underneath the header:

    paper-header-panel {
      --paper-header-panel-shadow: {
          height: 6px;
          bottom: -6px;
          box-shadow: inset 0px 5px 6px -3px rgba(0, 0, 0, 0.4);
      };
    }

To change the panel container:

    paper-header-panel {
      --paper-header-panel-container: {
        border: 1px solid gray;
      };

To change the panel container in different modes:

    paper-header-panel {
      --paper-header-panel-standard-container: {
        border: 1px solid gray;
      };

      --paper-header-panel-seamed-container: {
        border: 1px solid gray;
      };

      --paper-header-panel-waterfall-container: {
        border: 1px solid gray;
      };

      --paper-header-panel-waterfall-tall-container: {
        border: 1px solid gray;
      };

      --paper-header-panel-scroll-container: {
        border: 1px solid gray;
      };

      --paper-header-panel-cover-container: {
        border: 1px solid gray;
      };
    }

The following custom properties and mixins are available for styling:

Custom property | Description | Default
----------------|-------------|----------
`--paper-header-panel` | Mixin applied to the element | `{}`
`--paper-header-panel-body` | Mixin applied to the element's body (i.e. everything below the toolbar) | `{}`
`--paper-header-panel-container` | Mixin applied to the container in any mode | `{}`
`--paper-header-panel-scroll-container` | Mixin applied to the container when in scroll mode | `{}`
`--paper-header-panel-cover-container` | Mixin applied to the container when in cover mode | `{}`
`--paper-header-panel-standard-container` | Mixin applied to the container when in standard mode | `{}`
`--paper-header-panel-seamed-container` | Mixin applied to the container when in seamed mode | `{}`
`--paper-header-panel-waterfall-container` | Mixin applied to the container when in waterfall mode | `{}`
`--paper-header-panel-waterfall-tall-container` | Mixin applied to the container when in tall waterfall mode | `{}`
`--paper-header-panel-shadow` | Mixin applied to the waterfall shadow | `{}`

See: [Documentation](https://www.webcomponents.org/element/@polymer/paper-header-panel),
  [Demo](https://www.webcomponents.org/element/@polymer/paper-header-panel/demo/demo/index.html).

## Usage

### Installation
```
npm install --save @polymer/paper-header-panel
```

### In an html file
```html
<html>
  <head>
    <script type="module">
      import '@polymer/paper-header-panel/paper-header-panel.js';
      import '@polymer/paper-toolbar/paper-toolbar.js';
    </script>
    <style>
      html, body {
        margin: 0;
      }
      paper-header-panel {
        height: 100vh;
      }
    </style>
  </head>
  <body>
    <paper-header-panel>
      <paper-toolbar slot="header">Header</paper-toolbar>
      <div>Content goes here...</div>
    </paper-header-panel>
  </body>
</html>
```
### In a Polymer 3 element
```js
import {PolymerElement, html} from '@polymer/polymer';
import '@polymer/paper-header-panel/paper-header-panel.js';
import '@polymer/paper-toolbar/paper-toolbar.js';

class SampleElement extends PolymerElement {
  static get template() {
    return html`
      <style>
        paper-header-panel {
          height: 100vh;
        }
      </style>
      <paper-header-panel>
        <paper-toolbar slot="header">Header</paper-toolbar>
        <div>Content goes here...</div>
      </paper-header-panel>
    `;
  }
}
customElements.define('sample-element', SampleElement);
```

## Contributing
If you want to send a PR to this element, here are
the instructions for running the tests and demo locally:

### Installation
```sh
git clone https://github.com/PolymerElements/paper-header-panel
cd paper-header-panel
npm install
npm install -g polymer-cli
```

### Running the demo locally
```sh
polymer serve --npm
open http://127.0.0.1:<port>/demo/
```

### Running the tests
```sh
polymer test --npm
```
