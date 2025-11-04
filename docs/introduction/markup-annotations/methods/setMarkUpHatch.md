Sets a pre-defined hatch pattern fill for the selected markup object/annotation.
Only works for markup object/annotation that supports fill.



### Syntax

```typescript
RxCore.setMarkUpHatch(style)
```

### Parameters

- `style`: **number** — number id for the pre-defined hatch style.


### Hatch patterns
Use these values to set the hatch pattern fill.

| style         |  Pattern            |
| --------------|-------------------- |
| 0             | Forward Diagonal    |
| 1             | Backward Diagonal   |
| 2             | Diagonal Cross      |
| 3             | Horizontal          |
| 4             | vertical            |
| 5             | Cross               |



### Returns

- **NA** — This method does not return a value.