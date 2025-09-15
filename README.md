# Graphical Issues in Destiny 2 on Parallels ARM – Fixed via Boot Flag

## Problem  
When running Destiny 2 in a Windows ARM virtual machine (e.g. via Parallels on macOS), severe graphical glitches may occur:  
- Distorted objects  
- Flickering textures  
- “Exploding” character models  

These issues are especially common in missions with heavy shader usage or particle effects.

## Cause  
The GPU emulation in the VM struggles with certain dynamic shaders, particularly in DirectX 11-based games like Destiny 2.

## Solution  
A boot flag resolves the issue by adjusting how dynamic constant buffers are handled:


## How to Apply It  
1. Open Parallels → Configure your VM  
2. Go to **Hardware** → **Boot Flags** (under “Advanced”)
3. video.untrimmed_dynamic_cbuffers=1
5. Enter the flag above and save  
6. Restart the VM and launch Destiny 2

## Result  
The graphical issues disappear, shaders render correctly, and the game runs much more smoothly.

## Notes  
- Tested successfully on macOS 26 “Tahoe” using Parallels Desktop 2026  
- May also help with other DirectX 11 games showing similar problems  
- For best results, combine with:


This second flag disables DirectX 12 attempts and forces games to fall back to DirectX 11, which is better supported in Parallels.

---

Feel free to share or adapt this fix. If you encounter other VM-related issues with Destiny 2 or similar titles, contributions are welcome.
