Call to set canvas size based on web page content.
Ususally the call to RxCore.setLayout is followed by a call to RxCore.doResize();

See : [RxCore.doResize](./doResize)

### Syntax


```javascript
RxCore.setLayout({
  offsetWidth: 320,
  offsetHeight: 64,
  absolute: false
});

RxCore.doResize();
```



### Parameters

- `layout`: **object** — Object containing properties `offsetWidth` , `offsetHeight` and `absolute`.
    - `offsetWidth` expects values in pixels. 
    - `offsetHeight` expects values in pixels. 
    - `absolute` is a boolean that determine if the `offsetWidth` , `offsetHeight`are treated as margins - `false` or absolute values - `true`


### Returns

- **NA** — This method does not return a value.