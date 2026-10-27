# fast-sjis-encoder

Fast Shift-JIS(MS932) encoder - About 2.6x to 7x faster than iconv-lite

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
console.log(bytes); // Uint8Array(10) [72, 101, 108, 108, 111, 32, 144, 162, 138, 69]
```

## Benchmark

Comparison with iconv-lite 0.7.3 (operations per second, Japanese text, Node.js 24)

| chars | fast-sjis-encoder | iconv-lite | faster |
|------:|------------------:|-----------:|-------:|
|    30 |         6,002,207 |    858,178 |  6.99x |
|   300 |           575,400 |    222,539 |  2.59x |
|  3000 |            81,523 |     26,893 |  3.03x |

About 2.6x to 7x faster than iconv-lite.

## Decoder?

```javascript
const text = new TextDecoder('shift-jis').decode(bytes);
console.log(text); // "Hello 世界"
```

## License

MIT
