# Introducing usePageBloom: Simplify Pagination in Your Application
```markdown
`usePageBloom` is a customizable React package that provides pagination functionality and components for managing and displaying data in a paginated manner.

## Installation

To install the `usePageBloom` package, use the following command:

```bash
npm install use-page-bloom
```

## Usage

Import the `usePageBloom` hook from the package and use it within your React components to enable pagination for your data.

```jsx
import React from "react";
import usePageBloom from "use-page-bloom-hook";

function MyComponent({ data }) {
  const itemsPerPage = 10;
  const {
    currentPage,
    totalPages,
    currentData,
    goToPage,
    goToPreviousPage,
    goToNextPage,
  } = usePageBloom(data, itemsPerPage);

  return (
    <div>
      {/* Render your paginated data */}
    </div>
  );
}
```

## API

The `usePageBloom` hook returns an object with the following properties and methods:

- `currentPage: number`: The current active page.
- `totalPages: number`: The total number of pages based on the provided `data` and `itemsPerPage`.
- `currentData: T[]`: The data to display on the current page.
- `goToPage(page: number)`: Function to navigate to a specific page.
- `goToPreviousPage()`: Function to navigate to the previous page.
- `goToNextPage()`: Function to navigate to the next page.

### Example

```jsx
function MyComponent({ data }) {
  const itemsPerPage = 5;
  const pagination = usePageBloom(data, itemsPerPage);

  return (
    <div>
      {/* Render your paginated data */}
      {pagination.currentData.map((item, index) => (
        <div key={index}>{item}</div>
      ))}

      {/* Render pagination controls */}
      <button onClick={pagination.goToPreviousPage}>Previous</button>
      <button onClick={pagination.goToNextPage}>Next</button>
    </div>
  );
}
```

## Contributing

We welcome contributions! Feel free to open issues and pull requests on our [GitHub repository](https://github.com/your-repo-link).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```
