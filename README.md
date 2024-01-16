# GTA3LowEnd
GTA 3 fixed to run better on hardware at the time of release

At that time, the game received criticism for its high hardware requirements, and although nowadays it seems like meaningless nonsense, I have several reasons why I created this mod:

- I'm a collector of PCs and notebooks, and I like to play on period-correct hardware
- In the past, I tried running the game on the average popular hardware at the time (Pentium 2 ~350mhz, 8MB VRAM) and I discovered that the game would work, but with performance issues that at the time I didn't know how to fix
- When the game was ported to PC, it was done poorly (just like the overwhelming majority of Crapstar game ports), I tried to fix everything I could.

This project is not intended to be a base for you to play on your modern computer. Modern computers are already capable of running the game perfectly, using this mod on modern computers will only make the game uglier.

At that time, the game received criticism for its high hardware requirements, and although nowadays it seems like meaningless nonsense, I have several reasons why I created this mod:

- I'm a collector of PCs and notebooks, and I like to play on period-correct hardware
- In the past, I tried running the game on the average popular hardware at the time (Pentium 2 ~350mhz, 8MB VRAM) and I discovered that the game would work, but with performance issues that at the time I didn't know how to fix
- When the game was ported to PC, it was done poorly (just like the overwhelming majority of Crapstar game ports), I tried to fix everything I could.

This project is not intended to be a base for you to play on your modern computer. Modern computers are already capable of running the game perfectly, using this mod on modern computers will only make the game uglier.

What this project does:

- Uses many files (mainly texture) from the original version for PlayStation 2 (which has a lower resolution)
- Decreases the size of some textures across the map, which originally did not have enough definition for the resolution they were in (some 128x128 textures just looked like elongated versions of 64x64)
- Careful application of DXT1, DXT5, and palletizing compression methods (see note below)
- Careful Mipmap on many textures (see note below)
- Changing dat files to improve performance
- Removed the 12mb video memory restriction on the executable (requires exe 1.1)

* About DXT1 and DXT5 compression methods: Despite what they say, you CANNOT just go around compressing any texture. These algorithms work reasonably well with large textures (128x128, 256x256...) but can destroy the texture if it is too small. Very small textures can just use the palletizing method (using a 4 or 8 bit color palette which will decrease the file size, similar to a GIF file). The PlayStation 2 originally only supports the palletized format, and as the game was written with its hardware in mind, the overwhelming majority of the game's textures were created and optimized for the palletized format (with few colors), which is why in games of the era 3D, there is so much dithering/noise, and cartoonish appearance.

* About mipmaps: This is excellent for the video card, as it reduces the amount of calculations it has to do to fit the texture to the object depending on the distance. But there is a counterpoint that must be taken into consideration when specifying older hardware: Mipmaps use more RAM. Too much mipmap will considerably increase the load on RAM, so you should always take this into account. Textures used in the game's HUD and UI should never have mipmaps as they are always "close to the camera".


To do:

- Optimize the distribution of objects across the map. I tried using MEd to delete unnecessary objects, but unfortunately the game refuses to work, even though I review each file in notepad++ and remove the entries, I suspect there is something unplayable.

- The game has overdraw problems, this will probably only be resolved by editing the game's executable

- Check main.scm: I believe there may be some way to optimize it further (for example, optimizing the variables) but this, once again, would involve editing the executable.
