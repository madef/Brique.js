# Brique.js Documentation

## Overview

**Brique.js** is a minimalist template manager for JavaScript. It simplifies the process of creating and managing DOM elements dynamically.

**License**: MIT

## Example Usage

The following example creates a red button that displays an alert saying "Hello!" when clicked:

```javascript
const myButton = new Brique(`<button data-var="sayHello">Say Hello!</button>`)
  .classList('sayHello', classList => classList.add('bg-red-500'))
  .style('sayHello', style => style.background = 'rgb(239 68 68)')
  .addEventListener('sayHello', 'click', () => alert('Hello!'))
  .appendTo(document.getElementById('id'));
```

## Constructor

### `Brique(template, varAttribute = 'data-var', rootType = 'div')`

- **Description**: Creates a new template.
- **Parameters**:
  - `template` (string): The HTML template as a string.
  - `varAttribute` (string, optional): The attribute used to identify nodes. Default is `'data-var'`.
  - `rootType` (string, optional): The type of root element. Default is `'div'`.

## Methods

### `getChildren()`

- **Description**: Returns all nodes in the template.

### `get(identifier)`

- **Description**: Returns a specific node identified by `identifier`.
- **Parameters**:
  - `identifier` (string): The identifier of the node.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `appendTo(node, identifier)`

- **Description**: Injects the template into the `node`. If `identifier` is defined, injects the specific node identified by `identifier`.
- **Parameters**:
  - `node` (Element): The DOM element to append to.
  - `identifier` (string, optional): The identifier of the node within the template.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `append(identifier, node)`

- **Description**: Injects `node` into the template node identified by `identifier`.
- **Parameters**:
  - `identifier` (string): The identifier of the template node.
  - `node` (Element): The DOM element to append.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `prepend(identifier, node)`

- **Description**: Similar to `append`, but inserts `node` at the beginning of the template node identified by `identifier`.
- **Parameters**:
  - `identifier` (string): The identifier of the template node.
  - `node` (Element): The DOM element to prepend.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `empty(identifier)`

- **Description**: Empties the content of the node identified by `identifier`.
- **Parameters**:
  - `identifier` (string): The identifier of the node.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `remove(identifier)`

- **Description**: Removes the node identified by `identifier`. If `identifier` is not defined, removes all nodes.
- **Parameters**:
  - `identifier` (string, optional): The identifier of the node.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `call(identifier, callback)`

- **Description**: Executes `callback` on the node identified by `identifier`.
- **Parameters**:
  - `identifier` (string): The identifier of the node.
  - `callback` (function): The function to execute, receiving the node as an argument.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `style(identifier, callback)`

- **Description**: Manipulates the styles of the node identified by `identifier` using `callback`.
- **Parameters**:
  - `identifier` (string): The identifier of the node.
  - `callback` (function): The function to execute, receiving the style attribute of the node as an argument.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `classList(identifier, callback)`

- **Description**: Manipulates the class list of the node identified by `identifier` using `callback`.
- **Parameters**:
  - `identifier` (string): The identifier of the node.
  - `callback` (function): The function to execute, receiving the class list attribute of the node as an argument.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `addEventListener(identifier, type, callback, options)`

- **Description**: Attaches an event listener to the node identified by `identifier`.
- **Parameters**:
  - `identifier` (string): The identifier of the node.
  - `type` (string): The event type.
  - `callback` (function): The event handler function.
  - `options` (object, optional): Options for the event listener.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.

### `removeEventListener(identifier, type, callback, options)`

- **Description**: Detaches an event listener from the node identified by `identifier`.
- **Parameters**:
  - `identifier` (string): The identifier of the node.
  - `type` (string): The event type.
  - `callback` (function): The event handler function.
  - `options` (object, optional): Options for the event listener.
- **Throws**: `InvalidNodeIdentifier` if the identifier is unknown.
