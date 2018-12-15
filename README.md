# React Confirm
<!-- [![Build Status](https://travis-ci.org/codebraces/reconfirm.svg?branch=master)](https://travis-ci.org/codebraces/reconfirm) -->
[![npm Version](https://img.shields.io/npm/v/@braces/reconfirm.svg)](https://www.npmjs.com/package/@braces/reconfirm)


## Install
1 Install react confirm as dependency
  ```bash
  # Using yarn package manager
  $ yarn add @braces/reconfirm

  # Using npm package manager
  $ npm install --save @braces/reconfirm
  ```
2 Import React confirm module
  ```javascript
  // ES6
  import Confirm from "@braces/reconfirm"

  // ES5
  var Confirm = require("@braces/reconfirm");
  ```
## Example

#### [CodeSandbox Example Link](https://codesandbox.io/s/r46rpnw49m)
```javascript
  import React from "react";
  import ReactDOM from "react-dom";
  import Confirm from "@braces/reconfirm";

  function Component(props) {
    return (
      <div className="App">
        <button
          onClick={() =>
            props.confirm("Dialog Message", "Dialog Title", "Some Data", data => {
              alert(data + " Confirmed");
            })
          }
        >
          Show Confirm
        </button>
      </div>
    );
  }

  function Dialog(props) {
    return (
      <div className="App">
        <h1>{props.title}</h1>
        <h2>{props.message}</h2>
        <button onClick={props.onConfirm}>Confirm</button>
        <button onClick={props.onCancel}>Cancel</button>
      </div>
    );
  }

  const App = Confirm(Dialog)(Component);
  const rootElement = document.getElementById("root");
  ReactDOM.render(<App />, rootElement);
```

## Properties
### Component Props
| Name               | Type   | Description                                                          |
| :----------------- | :----- | :----------------- | :------------------------------------------------------------------- |
| confirm | (message?: string, title?: string, data?: any, onConfirmAction?: Function) => void | This is the function to invoke confirm dialog, *onConfirmAction* is callback function that will trigger with *data* as parameter when confirmed |
| confirmed | boolean | Here we can access confirm dialog status, whether confirmed or not |
| confirmData | any | Here we can access confirm data provided in *onConfirmAction* |

### Confirm Dialog Props
| Name               | Type   | Description                                                          |
| :----------------- | :----- | :----------------- | :------------------------------------------------------------------- |
| onConfirm | Function | Have to invoke *onConfirm* when the confirm button is pressed / clicked. |
| onCancel | Function | Have to invoke *onCancel* when the cancel button is pressed / clicked. |
| title | string | Here we can access *title* provided in *onConfirmAction* |
| message | string | Here we can access *message* provided in *onConfirmAction* |
| data | any | Here we can access *data* provided in *onConfirmAction* |


## Contributing!
All contributions are super welcome!


## License

React Confirm is MIT licensed.