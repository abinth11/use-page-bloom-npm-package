# usePageBloom Package Documentation

`usePageBloom` is a versatile React package that offers robust pagination functionality and components to seamlessly manage and display data in a paginated manner.

## Installation

To install the `usePageBloom` package, use the following command:

```bash
npm install use-page-bloom
```

## Usage

Import the `usePageBloom` hook from the package and incorporate it into your React components to effortlessly enable pagination for your data.

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

- `currentPage: number`: Represents the current active page.
- `totalPages: number`: Indicates the total number of pages, determined based on the provided `data` and `itemsPerPage`.
- `currentData: T[]`: Holds the data intended for display on the current page.
- `goToPage(page: number)`: A function to navigate directly to a specific page.
- `goToPreviousPage()`: A function to navigate to the previous page.
- `goToNextPage()`: A function to navigate to the next page.

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

We enthusiastically welcome contributions! Please feel free to open issues and submit pull requests on our [GitHub repository](https://github.com/your-repo-link).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.