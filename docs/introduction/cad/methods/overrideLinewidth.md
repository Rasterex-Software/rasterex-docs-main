Sets a minimum line width used when rendering CAD files.
Use this to ensure good CAD rendering visibility. 

Default values are on/true and 0.5 pixels. If this appear too thin, you can increase the value.

### Syntax

```typescript

RxCore.overrideLinewidth(true, 1); //set minimum thickness to 1 pixel.

```

### Parameters

- `onoff`: **boolean** — if true the override is on otherwise off.
- `thickness`: **number** — Width of minimum line thickness in pixels.

### Returns

- **NA** — This method does not return a value.