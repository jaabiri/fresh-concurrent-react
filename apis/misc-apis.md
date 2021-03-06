---
name: Misc APIs
menu: APIs
---

# Misc APIs

Other related APIs have been introduced with Concurrent React, but don't have official names as features.

## `React.lazy` Example

*Current API: `React.lazy`*

`React.lazy` allows lazy loading of components, ideal for code-splitting.

```js
import React, {lazy} from 'react'

// static
import button from './Button'

// dynamic, code split
const Button = lazy(() => import ('./Button))
```

## `React.pure` Example

*Current API: `React.pure`*

`React.pure` is a higher-order component version of the `React.PureComponent` class. 
During an update, the previous props are compared to the new props. 
If they are the same, React will skip rendering the component and its children.

Unlike userspace implementations, `pure` will not add an additional fiber to the tree.

The first argument must be a functional component; it does not work with classes.

pure uses shallow comparison by default, like `React.PureComponent`. 
A custom comparison can be passed as the second argument.

```js
const PureChildComponent = React.pure(ChildComponent)
```

--- 

**Recommended Sources for further info:**

- [React.pure PR](https://github.com/facebook/react/pull/13748)
- [React.lazy PR](https://github.com/facebook/react/pull/13398)