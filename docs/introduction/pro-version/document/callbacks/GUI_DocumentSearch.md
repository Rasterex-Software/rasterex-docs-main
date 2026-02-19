This callback event is triggered when `RxCore.documentTextSearch` is used.

### Version
(Pro version only)

### Callback Parameters

- **searchMatches**: An object that contains an array of objects that represnts the search result.


### Example:

```javascript
RxCore.GUI_DocumentSearch.connect(onGetMatches);

function onGetMatches(searchMatches) {


            this.searchNumMatches = 0;
            let id = 0;
            this.pageIndex = []
            searchMatches.forEach((match: any) => {
                this.searchNumMatches += match.list.length;
                    match.list.forEach(item => {
                        item.match.id = id
                        id ++;
                        this.pageIndex.push(match.pgindex)
                    })  
            })
            
            RxCore.forcetextsearchmarker(); //highlights the text that matches the search

            console.log(searchMatches)

  
  }
}
```
