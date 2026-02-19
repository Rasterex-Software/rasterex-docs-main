This callback event returns a markup object when that markup object has been consolidated.

### Callback Parameters
- `Markup` **object**: Markup object. See [Markup](../../markup-methods/intro.md#consolidate)


###  Example

```javascript
    RxCore.GUI_ConsolidateMarkup.connect(function(Markup){

        console.log("Markup consolidated", Markup.type);

    });

```
