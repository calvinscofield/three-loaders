### Usage

```js
npm i @calvinscofield/three-loader -S
import { OBJLoader, MTLLoader } from '@calvinscofield/three-loaders'
new OBJLoader()
  .load('model/penlin.obj', (object) => {},
  (xhr) => {
    console.log((xhr.loaded / xhr.total * 100) + '% loaded')
  },
  (error) => {
	  console.log(error, 'An error happened')
  })

new THREE.MTLLoader()
  .setPath('models/obj/male02/')
  .load('lqfy.mtl', function (materials) {
    materials.preload()
    new THREE.OBJLoader()
      .setMaterials(materials)
      .setPath('models/obj/male02/')
      .load('lqfy.obj', (object) => { scene.add( object )},
      (xhr) => { console.log((xhr.loaded / xhr.total * 100) + '% loaded') },
      (error) => { console.log(error, 'An error happened') })
  })
```
