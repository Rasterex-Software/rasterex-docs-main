Use this method to override values from the xml configuration loaded during startup. This must be called before `RxCore.initialize` to work.

### Example

```typescript

        let JSNObj = [
          {
              Command: "GetConfig",
              UserName: "Demo",
              DisplayName : "Demo User"
          }
        ];
        
        RXCore.setJSONConfiguration(JSNObj);

```

### Parameters

- `JSNObj`: **object** — A JSON structure that points to the configuration values to override.

### Returns

- **NA** — This method does not return a value.



