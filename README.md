# SylvaHero — Living Green

Integration of the **`SylvaHero`** component (`living-green` variant) from
[`@designcodeio/threeui`](https://www.npmjs.com/package/@designcodeio/threeui)
using its exact, byte-verified source.

## Usage

The component is rendered by `src/Scene.jsx` using the configured usage:

```tsx
import { SylvaHero } from "@designcodeio/threeui";
import "@designcodeio/threeui/style.css";

export function Scene() {
  return (
    <div className="shader-frame">
      <SylvaHero
        variant="living-green"
        headingFont="lexend"
        bodyFont="lexend"
        headingWeight="300"
        bodyWeight="300"
        primaryColor="#ffffff"
        headingSize={63}
        bodySize={16.5}
        headingLetterSpacing={-0.006}
      />
    </div>
  );
}
```

## How it works

`SylvaHero` renders the canonical, self-contained HTML document
`inner-green-3d.html` inside a sandboxed `<iframe>`. That document carries the
entire authored scene — the moss-root world, pale flowers, ferns, drifting
pollen, the landing butterfly, and the native liquid-metal controls behind the
full hero layout — together with its inline Three.js scene code and its local
`three.min.js` runtime.

The React wrapper (from the published package) resolves the typography props
(`headingFont`, `bodyFont`, weights, `primaryColor`, sizes, letter-spacing) and
injects the resulting CSS into the iframe document at runtime.

## Runtime files

The component expects its runtime files at the same root-relative URLs used by
the ThreeUI preview, so they live under `public/`:

```
public/landing-pages/inner-green-3d.html
public/landing-pages/inner-green-assets/three.min.js
public/landing-pages/inner-green-assets/card-ecostove.jpg
public/landing-pages/inner-green-assets/card-ethos.jpg
public/landing-pages/inner-green-assets/lexend-latin.woff2
```

All five files are byte-identical to the registered source (SHA-256 verified):

| File | SHA-256 |
| --- | --- |
| `inner-green-3d.html` | `69c3694bd63f44ef9f007ebe4dac57a83e4402e0cdf6b54dd10b96dd4f05e197` |
| `three.min.js` | `8a5f7249903b54d30f79f708699d2fed2d6a1d0741a4cd41377d1f01bb5a2271` |
| `card-ecostove.jpg` | `70ce084084902bc502f00c366405b661ecdff90dee95d363b36a6e146829e433` |
| `card-ethos.jpg` | `337627390f499b3ae272cec9e2f83c817694a82f42e1aa10a7b26a2c7d679dff` |
| `lexend-latin.woff2` | `1ec8f6ee2750554b4bc59ff0b507d316a82a7ba37e0e5bebc41d3bd9b9faad46` |

## Run

```bash
npm install
npm run dev      # http://localhost:5173
npm run build    # production build
```
