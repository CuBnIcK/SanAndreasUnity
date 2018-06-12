As the README list was very extensive, I have sum up here what I think it's important to implement inside alpha release 1.0:

## TODO

### Features

* Animations must be loaded/played by index – because different anim definition groups (man, woman, etc) use different anim names ( walk_civi, woman_walknorm, respectively).

* Weapons. Aiming with weapons – aim animation.

* What else can be imported: ai paths, character spawn info, item pickups, audio, 

* Rigid body character (on die or exiting a moving car, for example, like GTA IV)

* Load map in editor.

* Async geometry loading.

* Make everything networked.

- Two driving camera modes (aim to front and free look)

- Multiple car cameras: exterior (3 distance switches), interior & cinematic

- See the entire map (pressing M)

- Work on a menu like MTA:SA (F1)

- Dev profiles for the keyboard & mouse controls

- Health, stats (stamina, stength), money & armor system

- AI System for Peds

- Peds (and worker peds)

- Cars & fuel stations can explode

- Wheel explosion (I have to convert colliders, from a capsule collider generate a mesh collider with the shape of a capsule)

- In-game input manager

- Flip & repair cars

- CLI parameter for Console app to know where to connect (an IP)

- Collapse message logs

- Read sounds from GTA SA Streams: http://www.lysator.liu.se/~creideiki/radio-free-san-andreas/

- Make a paragraph for those categories: https://i.gyazo.com/07490f1d389fb3c4d6363e8d9810c0c1.png

- Maybe I will use my sockets implementation to do a server system (I will made a paid assets with [examples from Unity Forums](https://github.com/ZZona-Dummies/UnityForumsMultiplayer)

### Effects & Enhancements

* Jump, swim & fall animations (fall maybe reemplaced with rigidbody physics, when there is a big jump)

* Water effects (Swim, bouyancy, get darker and blurry the deeper you get)

* Work on props (lampposts, fences, etc)

* Decal system for Weapons

* Burnout trace

* Vehicle damage

* Dust and water particles with vehicles (cars travelling through dirt and boats, respectively)

* Stars, clouds and enviroment enhances

### Environment

* Weather system

### Vehicles

* Enhance car lights, turning, doors and braking
    
### Bugs to fix

- I have to fix this problem, modifying in some way Assembly Importer GUI to added to mark or something like that is saved to avoid it's compilation (https://cdn.discordapp.com/attachments/454006273751515163/455029337821806592/unknown.png) // I have fixed it, but now the inspector looks ugly

- Weird circular shadow appears when drving and the car passes next to a building that projects a shadow (low quality)

- Car moves when the player is still getting inside it

- Auto-zoom with big vehicles

- Some cars have its suppension to low to allow them to move

- Cars sometimes spawn under other cars, this makes that the cars jumps

- Make cars spawn appropiate for each zone

- When vehicles are damanged light goes weird

- Once vehicles are despawned they don't re-spawn

- In some cases damages to vehicles aren't performed at first collision

- Colors for debug messages in console

- HTML (from logger) indent is not perfect

- Console Application is not launching on build (CLI was checked and work properly)

- Sometimes in old gpus, all goes black, like for example here (https://i.gyazo.com/b3a682b86ab0808ca132bad803194cab.mp4) the way of fixing this is running Unity Editor undr `--force-glcore` and going to **Assets > Reimport all**

### Leaks

- Lagging when instantiating new lights

### Inneficiencies

- Curent socket system only allows messages of 8KBs

- Files with .log extension is printed in hexadecimal on Sublime Text (change extension)

### Must be reviewed

- If you regenerate scripts while running Unity Editor crashes (patch it?)

- Find in the project singletons and rename it to "me" if they are private and "instance" if they are public

- Running with `--force-glcore` makes Unity Editor slower when near objects has to be rendered

- I think that car light break system doesn't work fine

- HUGE REFACTOR (compiling Assembly into DLLs will solve most problems)

## What is UltraGTA?

UltraGTA is a project that I (z3nth10n) have been developing for about 3 - 4 months, it is able to read a custom GTA map and generate terrain, seas, rivers, roads, rails, houses, interiors and so on (for example: http://prtty.me/media/map-of-gta-united-states-grand-theft-auto-world-rpg-at-gta.png).

One of these days I will mix it with marvelous project.