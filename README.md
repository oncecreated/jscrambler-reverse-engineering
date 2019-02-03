# Control Flow Flattening
Transform from:

```js
console.log('hello');
var elements = [34, 56, 78];
for(var i = 0; i < elements.length; i++) {
    console.log(elements[i]);
}
console.log('world');
```

To:

```js
var l9kk = 56;
var elements = [34, 56, 78];
for(; l9kk != 46;) {
    switch (l9kk) {
        case 13:
            hh = elements[l];
            l9kk = 17;
            break;
        case 78:
            // dead code
            zz = 45
            break;
        case 45:
            g++;
            l++;
            l9kk = g < elements.length ? 13 : 40;
            break;
        case 56:
            var g = 0;
            var l = 0;
            var hh = undefined;
            var m = elements.length;
            l9kk = 77;
            break;
        case 40:
            console.log('world');
            l9kk = 46;
            break;
        case 77:
            console.log('hello');
            l9kk = 13;
            break;
        case 17:
            console.log(hh);
            l9kk = 45;
            break;
    }
}
```
