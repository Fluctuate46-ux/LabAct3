# CvSU Mini Store - Lab 3 Guide Questions

### 1. What is the difference between props and state?
- Props are inputs a parent component passes down to a child so the child knows what to display, like a product's title, price, or stock status[cite: 5].
- State is data a component keeps track of itself (like the cart count and last added item in `App.jsx`), and changing it tells React to re-render the screen[cite: 5].

### 2. Why can a child component not modify the props it receives?
- In React, props are meant to be read-only inside the child component so data only flows in one clear direction[cite: 5].
- If a child could change props on its own, it would be much harder to tell where updates are coming from when something breaks or behaves unexpectedly.

### 3. How does the `onAddToCart` callback allow data to flow from child to parent even though props only flow downward?
- `App.jsx` creates a function that updates the cart state and passes that function down to `ProductCard` through `onAddToCart`[cite: 5, 6].
- Even though the prop goes downward, clicking the button inside `ProductCard` calls that function and passes the product's `title` back up into `App.jsx`[cite: 5, 6].

### 4. Why is the `key` prop required when rendering a list with `.map()`? What could happen if it is missing or duplicated?
- React uses `key` to keep track of each item in a list across re-renders so it knows which element matches which data[cite: 5].
- Leaving it out can cause weird UI or state bugs when items change, and using duplicate keys can confuse React into updating or mixing up the wrong items.

### 5. What does the `children` prop allow you to do that a normal prop does not?
- `children` lets you put JSX elements—like a `Sale` or `New` badge—right inside `<ProductCard>...</ProductCard>` tags instead of passing everything as plain prop values[cite: 5].
- That makes it easy to customize what goes inside a card without adding extra props for every possible badge or element[cite: 5].
