# Turok VR Mod

Turok was one of my favorite games growing up on the Nintendo 64. Ever since I started using VR, I wanted to experience the original game properly in virtual reality, with stereoscopic 3D, roomscale movement, fully tracked weapons, physical interactions, and controls that feel natural in VR. So I eventually started building Turok VR.

The mod is made for the current PC version of Nightdive's Turok, which was upgraded to the KEX4 engine in 2025. Since it directly modifies the running PC game, this is a PCVR only project.

The biggest challenge is that there is no source code or proper documentation available for the game or the KEX4 engine. This makes development much more difficult than working on a normal mod for a well documented engine, an older engine with years of community knowledge, or an open source project where you can simply look at the code and change what you need. A lot of the work has been trial and error, finding out how the game behaves internally and then figuring out how to make VR work without breaking everything else.

The original weapon models were another major problem. They were built for a fixed first person camera and were often heavily incomplete because parts that were never visible on a normal monitor simply did not exist. In VR, where you can freely move and look around the weapon from different angles, many of these models were completely unsuitable.

Because of this, the weapons had to be rebuilt for VR. In many cases the original models were completed and reconstructed while keeping their original proportions, materials, and visual style as closely as possible. Some weapons were so incomplete that rebuilding them was no longer practical, so they were replaced with newly created models designed to stay faithful to the original look and style.

Despite these limitations, most of the major VR systems are now working. This includes full 6DoF head and weapon tracking, roomscale movement, motion controlled aiming, a hand mounted weapon wheel with slow motion selection, shoulder weapon slots, immersive climbing, a hand mounted HUD, full left handed controls, haptic feedback, comfort options, and many VR specific fixes for rendering, menus, weapons, and water.

Some features are still experimental. Immersive climbing can sometimes behave unpredictably, especially when entering or leaving climbable surfaces or moving over ledges. Quicksaving also has limitations because Turok was never really designed for unrestricted quicksaves. Many situations have been tested and several bugs have been fixed, but unusual game states or scripted events can still cause unexpected problems.

The goal is not to turn Turok into a different game, but to keep the original campaign, weapons, enemies, levels, secrets, pacing, and atmosphere intact while making it feel as natural as possible in VR.

At this point I have started the game so many times during development that it honestly feels like several thousand launches. I used to love the beginning of the first level. I am not sure I do anymore.

## Installation

> **Important: Vulkan is required for VR.** Turok VR is built around the Vulkan renderer and does not work with Direct3D. If you previously selected Direct3D in the Video Options, launch Turok in desktop mode first and switch the graphics API back to **Vulkan** before using the VR mod.

Turok VR runs **exclusively through OpenXR**. SteamVR or VDXR can be used as the OpenXR runtime. Make sure your preferred runtime is active before starting the game.

For the smoothest experience, **120 Hz is recommended in SteamVR or VDXR** if your headset and PC can handle it. Turok's original game logic, physics, enemies, and scripts still run at their safe internal rate of roughly 60 updates per second. The VR mod smooths and interpolates the visible movement between those game states so the headset can still be supplied at 72, 90, or 120 Hz without changing the speed of the game or its physics.

No special launch parameters, PowerShell scripts, or external setup tools are required. Copy `vulkan-1.dll`, `turok.assets`, and `steam_appid.txt` into your Turok installation folder and start the game normally through Steam. On the first launch, confirm the installation prompt. Turok VR will install the required files automatically and close the game once so everything can be loaded correctly on the next start.

After that, simply launch Turok normally through Steam again.

Default installation folder:

`C:\Program Files (x86)\Steam\steamapps\common\Turok`

All personal VR settings are stored in `TurokVRUser.ini`.

## Recommended HD Texture Pack

Turok has aged quite noticeably in terms of texture quality, even in the remastered PC version. This becomes much more obvious in VR because you can get much closer to walls, objects, weapons, and environmental details than you normally would on a monitor.

For that reason, I strongly recommend using the [iddqd_textures](https://www.moddb.com/mods/iddqd-textures) texture pack. It improves a large number of the original textures while keeping the overall visual style of the game intact.

Download:

https://www.moddb.com/mods/iddqd-textures/addons/iddqd

Extract the texture pack into the `mods` folder inside your Turok installation directory.

# Feature Overview

## Controller Layout

### Right-Handed

| Input | Left Controller | Right Controller |
|---|---|---|
| **Stick** | Move | Turn |
| **Stick Click** | Position Reset | Crouch |
| **Trigger** | Previous Weapon | Fire |
| **Face Button 1** | X: Map | A: Weapon Wheel |
| **Face Button 2** | Y: Menu | B: Alternate Ammo / Back |
| **Grip** | Next Weapon | Jump |

**Weapon Wheel:** Left Trigger = Left Shoulder Slot · Right Trigger = Right Shoulder Slot

### Left-Handed

| Input | Left Controller | Right Controller |
|---|---|---|
| **Stick** | Turn | Move |
| **Stick Click** | Crouch | Position Reset |
| **Trigger** | Fire | Previous Weapon |
| **Face Button 1** | X: Weapon Wheel | A: Map |
| **Face Button 2** | Y: Alternate Ammo / Back | B: Menu |
| **Grip** | Jump | Next Weapon |

**Weapon Wheel:** Left Trigger = Left Shoulder Slot · Right Trigger = Right Shoulder Slot

<a href="https://raw.githubusercontent.com/VinceCrusty/TurokVR/refs/heads/main/Media/Turok_Controls.jpg">
  <img src="https://raw.githubusercontent.com/VinceCrusty/TurokVR/refs/heads/main/Media/Turok_Controls.jpg" alt="Turok Controls" width="1000"/>
</a>


## Full VR Conversion

- **True stereoscopic VR rendering** - Turok is rendered as a real VR world instead of being displayed on a virtual screen.
- **OpenXR and Vulkan support** - Built around the game's Vulkan renderer and OpenXR for modern PCVR headsets.
- **Full 6DoF head tracking** - Look and move your head naturally in every direction.
- **Roomscale support** - Physical headset movement is translated into the game world, with movement direction following your view naturally.
- **6DoF motion-controlled weapons** - Weapons are independently tracked and aimed with the controller instead of being locked to the camera.
- **VR-ready weapon models** - Original weapon assets have been adjusted and completed where necessary so they can be viewed naturally from VR angles.
- **Automatic VR startup alignment** - Headset and weapon orientation are initialized correctly when entering the game.
- **Position reset** - Recenter the VR view at any time. Resetting also restores the correct weapon position.

## Weapons and Weapon Wheel

- **Hand-mounted weapon wheel** - The visual weapon wheel appears directly at your hand instead of as a fixed screen interface.
- **Slow-motion weapon selection** - Opening the weapon wheel slows the game down, giving you time to select a weapon without interrupting the action completely.
- **Safe weapon selection** - Movement and firing are temporarily disabled while the weapon wheel is open.
- **Natural weapon selection** - Point toward a weapon in the wheel and select it directly.
- **Shoulder weapon slots** - Assign favourite weapons to the left or right shoulder directly from the weapon wheel.
- **Left and right slot assignment** - Use the left or right trigger while selecting a weapon to assign it to the corresponding shoulder. The wheel displays an `L` or `R` marker.
- **Persistent shoulder configuration** - Shoulder assignments are stored with the save game.
- **Shoulder gestures** - Reach behind your shoulder to quickly draw assigned weapons such as the knife or bow.
- **Improved weapon positioning** - Weapon orientation and position are automatically corrected when changing weapons.
- **Optional weapon sway** - Walking weapon sway can be enabled or disabled.
- **Alternate ammunition support** - Alternate ammo is available directly from the VR controller layout.
- **VR-tuned bow aiming** - Bow, arrow orientation, weapon aiming, and crosshair alignment have been adjusted specifically for VR.
- **VR-tuned knife** - Includes corrected model orientation, swimming position, melee behaviour, and physical attack detection.

## Hands and Left-Handed Mode

- **Complete left-handed mode** - Swaps weapon hand, movement and turning controls, button roles, menus, HUD placement, and weapon behaviour.
- **Weapon hand display options** - Choose between no weapon hands, both hands, right-hand-only presentation, or immersive support-hand behaviour.
- **Immersive support hand** - In right-handed mode, moving the off hand toward a compatible weapon can display the support hand naturally on the weapon.
- **Left-handed support-hand limitation** - Automatic support-hand switching when approaching the weapon with the right hand is disabled in left-handed mode. The weapon hand models can only exist in one orientation and were originally designed for right-handed weapon handling, so dynamically mirroring this behaviour would produce incorrect hand placement.
- **Optional off hand** - The tracked off-hand representation can be enabled or disabled separately.
- **VR climbing hands** - Dedicated HD hands appear while climbing while weapons are hidden.
- **Hand-mounted HUD** - Health, ammunition, lifeforce, lives, and other status information can be displayed directly on the off hand.
- **HUD toggle** - The hand-mounted HUD can be completely enabled or disabled.

## Movement and Turning

- **Smooth analog movement** - Full analog stick movement replaces the original digital-style movement behaviour.
- **Head-oriented locomotion** - Movement direction can follow the headset for more natural roomscale navigation.
- **Smooth turning** - Continuous analog turning is available.
- **Snap turning** - Optional segmented turning with adjustable turn angle.
- **VR crouch control** - Crouching is available directly from the VR controller.
- **Reduced forced camera movement** - Head bobbing and other unwanted traditional first-person camera motion are minimized for VR.

## Immersive Climbing

- **Physical climbing** - Grab climbable surfaces using Grip or Trigger and pull yourself upward using your controllers.
- **Normal climbing** - Move yourself upward through natural controller movement.
- **Fast climbing** - Stronger upward controller motions can be used for faster climbing.
- **Automatic wall locking** - Optional assistance helps keep the player attached to climbable surfaces.
- **Ledge handling** - Reaching the top of a climbable wall attempts to transition the player cleanly onto the platform.
- **Natural detaching** - Release the wall, move away from it, or jump to detach.
- **Weapon handling while climbing** - Weapons are hidden and dedicated climbing hands are shown.
- **Classic climbing mode** - Physical climbing can be disabled entirely to restore the original climbing behaviour.
- **Climb camera assistance** - Original automatic climbing camera behaviour can be enabled or disabled independently.

> **Experimental feature:** Immersive climbing is still somewhat experimental and can occasionally behave unpredictably. Entering and leaving climbable surfaces, especially around ledges and unusual level geometry, may sometimes feel inconsistent or produce minor bugs. Classic climbing can be used instead if problems occur.

## Crosshair and Aiming

- **Convergent world-space crosshair** - The crosshair is calculated against the actual game world rather than being placed at a fixed VR depth.
- **Collision-aware placement** - Crosshair position reacts to world geometry and remains correctly visible in front of surfaces.
- **Accurate weapon alignment** - Weapon direction and crosshair position are synchronized for reliable aiming.
- **Crosshair customization** - Enable or disable it, change its size, and select its colour.

## VR Comfort Options

- **VR vignette** - Choose `OFF`, `WEAK`, `MEDIUM`, or `STRONG`.
- **Slope camera adjustment** - Automatic camera adjustment on slopes can be enabled or disabled and is disabled by default.
- **Water camera adjustment** - Camera behaviour while swimming can be controlled separately.
- **Head bobbing control** - Traditional movement-based camera motion can be disabled for a more comfortable VR experience.
- **Weapon sway control** - Walking sway can be switched independently from other comfort settings.
- **Weapon Camera Shake** - Enable or disable the rapid camera shake triggered by weapon fire. Turning it off removes the repeated visual kick that occurs with each shot, which can be uncomfortable in VR, especially with fast-firing weapons.
- **VR-specific defaults** - Settings that tend to cause discomfort or visual problems in VR use safer defaults.

## Graphics and VR Rendering

- **60 Hz game logic with higher VR refresh rates** - Turok's physics, enemies, scripts, and other game logic continue to update at roughly 60 Hz to preserve the original timing. The visible VR presentation is interpolated between those states and can be delivered to the headset at 72, 90, or 120 Hz.
- **120 Hz recommended** - For the smoothest presentation, 120 Hz is recommended in SteamVR or VDXR when supported by the headset and available performance. The game also works at lower OpenXR refresh rates.
- **Optimized stereo rendering** - The scene no longer needs to be fully calculated twice for every frame. The second eye can reuse the already recorded Vulkan rendering work with the appropriate eye view, greatly reducing the CPU cost of stereoscopic rendering.
- **Synchronized stereo frames** - Both eyes use the same game state, reducing the temporal offset and doubled edges that could previously appear on moving objects.
- **OpenXR-aware interpolation** - KEX interpolation is driven by the actual OpenXR refresh rate instead of depending on the desktop monitor refresh rate.
- **Improved frame timing** - OpenXR frame timing is better synchronized with Turok's renderer for smoother headset motion and presentation.
- **VR-correct water rendering** - Water shaders and reflections have been repaired for stereoscopic rendering.
- **Water refraction** - Enabled by default.
- **Optional water reflections** - Reflections are available but disabled by default for VR performance and compatibility.
- **Stereo GUI fixes** - Interface elements that previously appeared in only one eye are rendered correctly.
- **Improved desktop mirror** - A stable left-eye spectator view is shown on the monitor without the previous flickering.
- **VR resolution presets** - Practical VR resolutions are available from the Video menu and can be applied with a restart.

> **Water reflection warning:** Water reflections are not yet fully correct in VR. Some reflections may contain visual artifacts that do not belong there and can be irritating to the eye. They are usually barely noticeable, but are particularly visible in the water near the beginning of Level 1. I am still working on resolving this issue.

## Menus and Interface

- **Dedicated VR Options menu** - VR settings are organized into logical Weapons, Controls, Visuals, Comfort, and related categories.
- **Controller-driven menus** - Menus can be operated completely from the VR controllers.
- **VR menu pointer** - A tracked pointer provides mouse-like menu interaction from inside the headset.
- **VR-scaled menus** - Pause and other menus have been repositioned and resized for headset viewing.
- **VR-adjusted cheat menu** - The original cheat interface remains available and is aligned correctly in VR.
- **VR title presentation** - Turok VR uses its own VR title presentation while leaving the original game content intact.
- **Controller reference layouts** - Dedicated control diagrams are available for both right-handed and left-handed configurations.

## Haptic Feedback

Separate vibration controls are available for different types of interaction:

- **Weapons**
- **Damage**
- **Environmental effects**
- **Climbing**

Each category can be adjusted independently.

## Saving and Quicksaves

- **Quicksave and quickload** - Both are accessible while playing in VR.
- **Timestamped quicksaves** - Quicksaves include date and time information.
- **VR state persistence** - VR-specific gameplay information such as shoulder weapon assignments is stored with the save game.
- **Bonus-level save handling** - Additional handling improves quicksave behaviour inside Turok's bonus areas.
- **Reliable VR configuration** - User configuration is preserved when reinstalling or updating the mod.

> **Quicksave warning:** Turok was not originally designed around unrestricted quicksaving. Although many situations have been tested and several known problems have been addressed, it is impossible to test every level state, scripted event, boss encounter, bonus area, or unusual gameplay situation. Quicksaving at unexpected moments may therefore cause unforeseen bugs or incorrect game states. Regular save points should still be used whenever possible.

## Configuration and Diagnostics

- **Single user configuration file** - User-adjustable VR settings are collected in `TurokVRUser.ini`.
- **Custom controller bindings** - VR button assignments can be changed through the configuration.
- **Optional diagnostic logging** - Set `ActivateLogs=1` under `[Diagnostics]` to generate troubleshooting logs.
- **Protected internal settings** - Critical VR configuration and resources are contained inside the VR component to reduce accidental configuration problems.

## Installation and Reliability

- **Self-contained VR assets** - VR-specific assets are separated from the original game files.
- **Automatic component installation** - Required VR components and OpenXR files are installed with the mod.
- **Uninstaller included** - The VR modification can be removed without manually searching for installed files.
- **Steam installation handling** - Additional handling allows the game to start correctly even in installations where the original Turok directory has been renamed.

## Original Turok Remains Intact

Turok VR is designed around the original game rather than replacing it.

The complete single-player campaign, enemies, dinosaurs, weapons, keys, artefacts, portals, secrets, cheat menu, bonus stages, boss fights, save system, and classic gameplay remain intact while the presentation and controls are adapted for virtual reality.

## Uninstallation

Close Turok and run `TurokVR-Uninstall.cmd` from the Turok installation folder. Your save games and `TurokVRUser.ini` are preserved.

The original `kexengine.cfg` is backed up once as `kexengine.cfg.pre-turokvr.bak`.

## Bugs, Issues and Feedback

Turok VR modifies a closed source game and engine through reverse engineering, so unexpected behavior can still occur even in areas that appear unrelated to VR.

If you encounter a reproducible problem, please report it through GitHub Issues:

https://github.com/VinceCrusty/TurokVR/issues

When possible, include what you were doing when the problem occurred, the level or area, whether the issue can be reproduced, your OpenXR runtime, your headset, relevant VR settings, and a log created with `ActivateLogs=1` if available.
