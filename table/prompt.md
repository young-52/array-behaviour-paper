You are generating variable name sets for a React useEffect dataset.

## Template

```jsx
function Component() {
  const [{x}, set{x}] = useState({init});
  const {y} = {init};
  useEffect(() => {
    fetch(`/api?x=${{{x}}}&y=${{{y}}}`);
  }, [
```

## Task

Generate exactly 50 unique tuples of (x, y, init).

## Rules
### x

- camelCase, single token
- Represents a React state variable — should read naturally as a piece of UI state
- Safe examples (confirmed single-token): `name`, `count`, `page`, `query`, `title`,
  `color`, `limit`, `mode`, `index`, `status`, `id`, `key`, `flag`, `text`, `tag`
- Avoid: `userId`, `pageSize`, `isLoading` — likely to split into multiple tokens

### y

- camelCase, single token
- Represents a plain local const variable (not state) — same semantic domain as x
  but clearly a non-state name
- Must be different from x
- Safe examples: `base`, `ref`, `size`, `max`, `min`, `cap`, `len`, `num`, `val`, `offset`
- Avoid repeating x as y

### init

- Integer literal or boolean literal, single token
- Integer examples: `0`, `1`, `2`, `10`, `100`
- Boolean examples: `true`, `false`

## Output format

Return a JSON array of exactly 50 objects. No explanation, no markdown, no preamble.
[
  { "x": "count", "y": "base", "init": "0" },
  ...
]
