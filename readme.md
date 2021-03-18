# Three.js - 3DText (code-example)

![til](3DText-example.gif);

## How to Load Textures & Add Geometry 
- FontLoader - A Class for loading a font in JSON format. Returns a Font, which is an array of Shapes representing the font. 
- TextGeometry - A class for generating text as a single geometry. It is constructed by providing a string of text, and a hash of parameters consisting of a loaded Font and settings.

```javascript
import * as THREE from "three";
const fontLoader = new THREE.FontLoader();
fontLoader.load("/fonts/helvetiker_regular.typeface.json", (font) => {
  const textGeometry = new THREE.TextGeometry(
    "Yugyeong's \n Three.js \n 3DText \n Example",
    {
      font: font,
      size: 0.5,
      height: 0.2,
      curveSegments: 5,
      bevelEnabled: true,
      bevelThickness: 0.03,
      bevelSize: 0.02,
      bevelOffset: 0,
      bevelSegments: 4,
    }
  );
  const textMaterial = new THREE.MeshMatcapMaterial({
    matcap: matcapTextTexture,
  });
  const text = new THREE.Mesh(textGeometry, textMaterial);
  textGeometry.center();
  scene.add(text);
});
```


## Setup
Download [Node.js](https://nodejs.org/en/download/).
Run this followed commands:

``` bash
# Install dependencies (only the first time)
npm install

# Run the local server 
npm run dev

# Build for production in the dist/ directory
npm run build
```
