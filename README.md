# PlatformerLab

My Unity project for the ASE Multimedia lab. This checkpoint follows the course through

## Open and play

- **A / D** or **Left / Right arrows**: walk.
- A gamepad's left stick also controls movement through the template's `Player/Move` action.
- The astronaut faces the direction of movement and stops against either crate wall.
- Gravity is **0** at this checkpoint. Exercise 6 starts gravity; jumping and ground detection come later in week 3.

## Course checkpoint

| Course step | Project state |
| --- | --- |
| Project setup / Exercise 1 | Universal 2D, Unity 6000.6, Input System, Force Text, Visible Meta Files, Unity `.gitignore`, GitHub remote |
| Exercise 2 | 180 terrain tiles: Single, PPU 18, Full Rect, Point filtering, no compression |
| Character sheet | `Assets/Sprites/tilemap-characters_packed.png`: 27 frames, 24 × 24 pixels, bottom pivots, PPU 18 |
| Sorting layers | Default → Background → Level → Characters → Foreground |
| Exercise 3 | `PlatformerPalette` in `Assets/Tiles`; ten grass cells at y = −3, two crates above each end |
| Exercise 4 | Ground: Tilemap Collider 2D + Composite Collider 2D, Merge, Static Rigidbody 2D |
| Walker | Position (0, −2, 0), Characters sorting layer, Dynamic body, gravity 0, Continuous detection, Interpolate, Freeze Rotation Z |
| Walker collider | Box size (0.9, 1.27), offset (0, 0.635) |
| Exercise 5 | `WalkerController`: speed 6, cached references in `Awake`, input in `Update`, velocity in `FixedUpdate`, facing via `flipX`, preserved vertical velocity |
| Prefab practice | `Assets/Prefabs/Walker.prefab` holds the tuned components; the scene uses a connected instance |

The original sprite GUIDs, frame identities, scene GUID, and sorting-layer identities are preserved. `SampleScene` and the Universal 2D template assets are retained. `MovementLab` is the first enabled build scene.

## Original asset packs

The setup guide asks for pristine asset packs **outside** the Unity project. On this computer they are in `C:\Users\IKeep\CourseAssets`, with one folder and the original ZIP for each pack:

- PixelPlatformer
- InterfaceSounds
- ImpactSounds
- MusicJingles


Run these from the repository folder. Save the Unity scene and project before committing.

```sh
git pull
git status
git add .
git commit -m "Describe the exercise you completed"
git push
```


## References

- [Project setup](https://docs.lucianvilcea.ro/multimedia/creating-the-project)
- [Exercise 2: The art, ready to use](https://docs.lucianvilcea.ro/multimedia/exercise-2-the-art-ready-to-use)
- [Exercise 3: A tiled room](https://docs.lucianvilcea.ro/multimedia/exercise-3-a-tiled-room)
- [Exercise 4: A walker with a body, on a solid floor](https://docs.lucianvilcea.ro/multimedia/exercise-4-a-walker-with-a-body-on-a-solid-floor)
- [Exercise 5: A walker that walks](https://docs.lucianvilcea.ro/multimedia/exercise-5-a-walker-that-walks)
- [End-of-week-2 summary](https://docs.lucianvilcea.ro/multimedia/summary-assets-tilemaps-and-the-first-script)
