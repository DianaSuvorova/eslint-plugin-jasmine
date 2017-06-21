# Enforce new line before expect inside a suite

This rule enforces that there is an empty line before `expect`.

## Rule details

This rule triggers a **warning** (is set to **1** by default) whenever there is no new line before expect.

The following patterns are considered warnings:

```js
describe("", function() {
  it("", function() {
    expect(1).toBe(1);
  });
});
```

```js
describe("", function() {
  it("", function() {
    var a = 1;
    expect(a).toBe(1);
  });
});
```

The following patterns are not warnings:

```js
describe("", function() {
  it("", function() {

    expect(1).toBe(1);
  });
});
```

```js
describe("", function() {
  it("", function() {
    var a = 1;

    expect(a).toBe(1);
  });
});
```