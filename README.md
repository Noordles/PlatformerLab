# PlatformerLab

My Unity project for the ASE Multimedia lab. This checkpoint follows the course through **Exercise 5: A walker that walks**, ready to begin week 3.

## Open and play

On the classroom PC, clone the repository or use **Code → Download ZIP** on [GitHub](https://github.com/Noordles/PlatformerLab). Extract the ZIP into a local folder outside OneDrive. In Unity Hub, use **Add project from disk** and select the folder containing `Assets`, `Packages`, and `ProjectSettings`. Use the classroom's Unity **6000.6.x** editor. The project retains its original version record, `6000.6.0f1`.

Open `Assets/Scenes/MovementLab.unity`, press Play, and click the Game view. No Unity installation on my laptop is required to download this checkpoint.

On the classroom PC, also check **Edit → Preferences → External Tools → External Script Editor** and select **Visual Studio [18.x] / Visual Studio 2026**, as Exercise 2 specifies. This is a per-computer Unity preference and is not stored in GitHub.

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

Only the required artwork is imported at this checkpoint. Audio remains staged for later lessons. These outside folders are local source material and are not included in this Git repository. **Everything needed for the week 2 scene is included in GitHub**, so the classroom PC does not need this local `CourseAssets` folder to open it. See [CREDITS.md](CREDITS.md) for asset sources and licensing.

## Verification and first classroom check

The checkpoint was checked against the exercise instructions at the file level: Unity YAML syntax, scene and prefab object references, asset GUIDs, the 27 frame definitions, terrain import settings, input bindings, physics settings, and build-scene assignment. The report is in [Verification/week-2-file-checks.txt](Verification/week-2-file-checks.txt).

**Unity compilation and Play Mode were not run on this laptop.** On the classroom PC, after import finishes:

1. Open `MovementLab` and press Play. The Console should report `Awake: rb=True, sr=True, move=True` without errors.
2. Click the Game view, press A and D or the arrow keys, and check movement and facing. Releasing the keys should stop movement and keep the last facing.
3. Walk into each crate wall and confirm it stops the walker. The walker should remain at floor height because gravity is 0.
4. Stop Play before changing anything. Begin [Exercise 6: A walker that falls](https://docs.lucianvilcea.ro/multimedia/exercise-6-a-walker-that-falls) for week 3.

## Git workflow

Run these from the repository folder. Save the Unity scene and project before committing.

```sh
git pull
git status
git add .
git commit -m "Describe the exercise you completed"
git push
```

Generated Unity caches, logs, build output, and IDE files are ignored. Pulls use rebase in this local checkout. The repository remains **public**, by my choice; the course's Exercise 1 suggests private visibility.

## References

- [Project setup](https://docs.lucianvilcea.ro/multimedia/creating-the-project)
- [Exercise 2: The art, ready to use](https://docs.lucianvilcea.ro/multimedia/exercise-2-the-art-ready-to-use)
- [Exercise 3: A tiled room](https://docs.lucianvilcea.ro/multimedia/exercise-3-a-tiled-room)
- [Exercise 4: A walker with a body, on a solid floor](https://docs.lucianvilcea.ro/multimedia/exercise-4-a-walker-with-a-body-on-a-solid-floor)
- [Exercise 5: A walker that walks](https://docs.lucianvilcea.ro/multimedia/exercise-5-a-walker-that-walks)
- [End-of-week-2 summary](https://docs.lucianvilcea.ro/multimedia/summary-assets-tilemaps-and-the-first-script)
