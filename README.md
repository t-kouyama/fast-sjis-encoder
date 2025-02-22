# fast-sjis-encoder

Fast Shift-JIS(MS932) encoder - About 2x faster than iconv-lite

## Installation

```bash
npm install fast-sjis-encoder
```

## Usage

Browser
```html
<script src="https://cdn.jsdelivr.net/npm/fast-sjis-encoder"></script>
```

ES Modules
```javascript
import sjis from 'fast-sjis-encoder';
```

CommonJS
```javascript
const sjis = require('fast-sjis-encoder');
```

Encode string to Shift-JIS byte array
```javascript
const bytes = sjis('Hello 世界');
console.log(bytes); // Uint8Array(10) [72, 101, 108, 108, 111, 32, 144, 162, 138, 91]
```

## Benchmark

Comparison with iconv-lite (operations per second)

| chars | fast-sjis-encoder | iconv-lite | faster |
|------:|------------------:|-----------:|-------:|
|    30 |         1,491,271 |    789,446 |  1.89x |
|   300 |           471,622 |    222,128 |  2.12x |
|  3000 |            61,771 |     24,708 |  2.50x |

About 2x faster than iconv-lite.

## Decoder?

```javascript
const text = new TextDecoder('shift-jis').decode(bytes);
console.log(text); // "Hello 世界"
```

## License

MIT
