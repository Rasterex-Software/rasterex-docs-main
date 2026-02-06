There are some options on setting user with the Rasterex Web SDK.
If the server configuration allow you to override the current user you can use the setUser method.


```typescript
    RxCore.setUser(sign, disp);
```

- `sign`: Unique identifier for the user.
- `disp`: Friendly display name to present for the user.

Using this option require the below permission is set in the [defaultconfig.xml](../../../server/#defaultconfigxml) file.




```XML
<CanChangeSignature>True</CanChangeSignature>
```
