
# @precooked/react-play-pause-cell

The `PlayPauseCell` component is a reusable React component designed to toggle between a "play" and "pause" state. It integrates with an HTTP client for server communication and provides customizable callbacks for handling success and error states.

![Precooked Logo](https://precookedcode.com/assets/logos/logo-horizontal-dark.svg)

## Installation

To install the package, use the following command:

```bash
npm install @precooked/react-play-pause-cell
```

## Usage

Here's an example of how to use the `PlayPauseCell` component:

```tsx
import React, { useState } from "react";
import { PlayPauseCell } from "@precooked/react-play-pause-cell";

const App = () => {
  const [isPlaying, setIsPlaying] = useState(false);

  const handleSuccess = (newValue: boolean) => {
    console.log("Success:", newValue);
    setIsPlaying(newValue);
  };

  const handleError = (error: any) => {
    console.error("Error:", error);
  };

  return (
    <PlayPauseCell
      value={isPlaying}
      size="md"
      endpoint="/api/play-pause"
      apiBaseUrl="https://api.example.com"
      useInterceptor={true}
      onChangeSuccess={handleSuccess}
      onChangeError={handleError}
    />
  );
};

export default App;
```

## Props

| Prop Name        | Type                                  | Default  | Description                                                      |
|-------------------|---------------------------------------|----------|------------------------------------------------------------------|
| `value`          | `boolean`                            | `true`   | The initial state of the cell (play or pause).                   |
| `size`           | `"xs" \| "sm" \| "md" \| "lg" \| "xl"` | `"md"`   | Size of the component.                                           |
| `className`      | `string`                              | `undefined` | Optional class name for custom styling.                          |
| `style`          | `React.CSSProperties`                | `undefined` | Inline styles for the container.                                |
| `apiBaseUrl`     | `string`                              | `undefined` | Base URL for the HTTP client.                                    |
| `endpoint`       | `string`                              | `required` | Endpoint for the HTTP request.                                   |
| `useInterceptor` | `boolean`                            | `false`  | Whether to use interceptors with the HTTP client.                |
| `onChangeSuccess`| `(newValue: boolean) => void`        | `undefined` | Callback invoked on successful state change.                    |
| `onChangeError`  | `(error: any) => void`               | `undefined` | Callback invoked when an error occurs.                          |

## Features

- Toggle between "play" and "pause" states.
- Customizable sizes: `xs`, `sm`, `md`, `lg`, `xl`.
- Integration with an HTTP client for server communication.
- Callbacks for success and error handling.
- Fully customizable via `className` and `style` props.

## License

MIT © [Precooked Code](https://precookedcode.com)
