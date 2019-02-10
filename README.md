# Control Flow Flattening

```js
console.log('hello');
var elements = [34, 56, 78];
for(var i = 0; i < elements.length; i++) {
    console.log(elements[i]);
}
console.log('world');
```
tranform to:

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

# String Concealing
```js
console.log('hello world');
console.log('re is not nightmare')
```
transform to
```js
var K9TT = function() {};
K9TT.J7E = function () {
    return {
        // decoding xored content
        L8: function(b90) {
            // in real - with control flow flattening
            var S4KK = decodeURIComponent("%2FU%5C%28%28%14%3A%5C5%5CTg%18F%28%13.C%10%2A%28%40m%5D.WX0%2AU%3FV");
            var SO9T = [];
            for(var i = 0; i < S4KK.length; i++){
	            SO9T.push(String.fromCharCode(S4KK.charCodeAt(i) ^ b90.charCodeAt(i % b90.length)))
            }
            SO9T = SO9T.join('');
            var M0R3 = SO9T.split('#_');
            return function (h67) {
                return M0R3[h67];
            }
        }('G00DG4M3')
    }
}();
// resolver function, may be multiple
K9TT.RY5 = function () { return K9TT.J7E.L8.apply(K9TT.J7E.L8, arguments); };

// constants, used for simple math with resolver
var H9AA = "9780";
var J990 = "9780";
var FD0U = "-9781";
var XZ88 = 1;

// +H9AA-J990 = 0, we take first element
console.log(K9TT.RY5(+H9AA-J990));
// -FD0U-J990 * XZ88 = 1, we take second element
console.log(K9TT.RY5(-FD0U-J990 * XZ88))
```
