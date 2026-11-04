# Portal Adventure 3D — modèles externes

Le prototype charge les fichiers 3D avec **Three.js / GLTFLoader**.

## Configuration
Modifier `assets.json` :
- `character.path` : chemin relatif vers un modèle `.glb` ou `.gltf`, par exemple `../3D/personnages/hero.glb` **uniquement si ce fichier existe réellement**.
- `character.scale` : taille du personnage ; `yOffset` : ajustement vertical.
- `scenery` : tableau d'objets `{ "path": "../3D/decor.glb", "position": [0,0,-15], "rotationY": 0, "scale": 1 }`.

Le fichier est volontairement vide : les chemins réels des assets du dépôt n'ont pas encore été vérifiés. Ne pas inventer les chemins.

Les modèles GLB embarquent généralement leurs textures. Pour GLTF, conserver les fichiers `.bin` et textures référencés avec leur structure de chemins.

Si aucun asset n'est configuré ou si un chargement échoue, les formes provisoires restent visibles. Les clips d'animation embarqués sont lus ; les clips portant un nom de type `Idle`, `Walk` ou `Run` sont utilisés pour les animations de repos et de déplacement.

## Tester
Servir le dépôt par un serveur HTTP (GitHub Pages ou serveur local), et ouvrir `adventure-3d/index.html`. Ne pas ouvrir directement en `file://` : les modules et `fetch` peuvent être bloqués.

## À vérifier avant publication
- Inventaire exact des modèles et animations dans le dépôt
- Licences de redistribution et de publication
- Compatibilité glTF/GLB, poids, textures, orientation et échelle
- Test réel dans le navigateur sur ordinateur et mobile
