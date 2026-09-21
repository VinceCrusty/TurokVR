# Turok VR - Features

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

**Context-sensitive Trigger:** When the off hand is attached to a weapon, Trigger holds/releases the immersive support-hand grip and normal Trigger weapon switching is temporarily disabled.

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
- **Knife mode: BOTH by default** - Use the classic trigger-based automatic knife attack and immersive physical melee at the same time.
- **Tomahawk support** - Adds a dedicated Tomahawk weapon with its own VR model, hand setup, HUD icon, calibrated position, and VR weapon-selection support.
- **Tomahawk quick selection** - The Tomahawk can also be selected from the off hand by using Grip while pointing at the knife entry.
- **Weapon wheel presentation** - The equipped weapon is hidden while the weapon wheel is open so it does not obstruct selection.

## Hands and Left-Handed Mode

- **Complete left-handed mode** - Swaps weapon hand, movement and turning controls, button roles, menus, HUD placement, and weapon behaviour.
- **Weapon hand display options** - Choose between no weapon hands, both hands, right-hand-only presentation, or immersive support-hand behaviour.
- **Immersive support hand** - Move the off hand into the calibrated attachment area and hold Trigger to attach it to a compatible weapon. Release Trigger to detach it again. Normal Trigger weapon switching is temporarily disabled while the support hand is attached.
- **Immersive support hand for left-handed mode** - Weapon-hand models are mirrored for left-handed play, allowing immersive support-hand attachment to work in left-handed mode as well.
- **Two-handed weapon handling** - While the support hand is attached, moving the off hand also influences the weapon position and orientation for more natural two-handed control.
- **Hide HUD on Immersive Grip** - Enabled by default. The wrist HUD is automatically hidden while the immersive support hand is attached to a weapon.
- **Optional off hand** - The tracked off-hand representation can be enabled or disabled separately.
- **VR climbing hands** - Dedicated HD hands appear while climbing while weapons are hidden.
- **Hand-mounted HUD** - Health, ammunition, lifeforce, lives, and other status information can be displayed directly on the off hand.
- **HUD toggle** - The VR HUD can be switched between three modes: ON (hand-mounted HUD), CLASSIC (a smaller, head-locked version of the original HUD near the lower-left of the view), and OFF (completely disabled).
- **Left-handed Classic HUD support** - The fixed Classic HUD is correctly positioned and mirrored for left-handed mode.
- **Automatic pause handling** - Weapon, off hand, and wrist HUD are hidden automatically while the Pause Menu is open.
- **Cutscene hand hiding** - Tracked hands are hidden during cutscenes.
- **Improved off-hand stability** - Off-hand positioning has been improved while crouching, landing after jumps, moving, changing direction, starting a game, and loading between sections.

## Movement and Turning

- **Smooth analog movement** - Full analog stick movement replaces the original digital-style movement behaviour.
- **Head-oriented locomotion** - Movement direction can follow the headset for more natural roomscale navigation.
- **Smooth turning** - Continuous analog turning is available.
- **Smooth turn speed** - Choose `FAST`, `MEDIUM`, or `SLOW` for smooth turning. `MEDIUM` is the default, and the option is disabled while Snap Turning is active.
- **Snap turning** - Optional segmented turning with adjustable turn angle.
- **VR crouch control** - Crouching is available directly from the VR controller.
- **Reduced forced camera movement** - Head bobbing and other unwanted traditional first-person camera motion are minimized for VR.

## Immersive Climbing

- **Physical climbing** - Grab climbable surfaces using Grip or Trigger and pull yourself upward using your controllers.
- **Normal climbing** - Move yourself upward through natural controller movement.
- **Fast climbing** - Stronger upward controller motions can be used for faster climbing.
- **Automatic wall locking** - Optional assistance helps keep the player attached to climbable surfaces.
- **Collision-aware immersive climbing** - Immersive climbing now checks wall collision to keep grabbing behaviour better aligned with the actual climbable surface.
- **More forgiving grip release** - The fall/release threshold is slightly increased so you do not need to re-grab the wall as quickly while climbing.
- **Ledge handling** - Reaching the top of a climbable wall attempts to transition the player cleanly onto the platform.
- **Natural detaching** - Release the wall, move away from it, or jump to detach.
- **Weapon handling while climbing** - Weapons are hidden and dedicated climbing hands are shown.
- **Climbing mode: BOTH by default** - Normal automatic climbing and immersive climbing can be used together. While climbing normally, simply grab the wall to switch directly into immersive climbing.
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
- **Extended Draw Distance** - A new option under `VR Options > Visuals` increases draw distance from the original `DEFAULT (1x)` through `2x` to `7x`, with `MAX (8x)` extending it beyond the game's normally allowed value. Higher settings can reduce performance or cause unexpected issues and should be used with caution.
- **Updated colour defaults** - The default and `Color Defaults` reset values are Saturation `1.40`, Contrast `1.05`, and Brightness `-0.06`.

> **Water reflection warning:** Water reflections are not yet fully correct in VR. Some reflections may contain visual artifacts that do not belong there and can be irritating to the eye. They are usually barely noticeable, but are particularly visible in the water near the beginning of Level 1. I am still working on resolving this issue.

## Menus and Interface

- **Dedicated VR Options menu** - VR settings are organized into logical Weapons, Controls, Visuals, Comfort, and related categories.
- **Controller-driven menus** - Menus can be operated completely from the VR controllers.
- **VR Options Back control** - The Y button can be used as Back inside the VR Options menus.
- **VR menu pointer** - A tracked pointer provides mouse-like menu interaction from inside the headset.
- **VR-scaled menus** - Pause and other menus have been repositioned and resized for headset viewing.
- **VR-adjusted cheat menu** - The original cheat interface remains available and is aligned correctly in VR.
- **VR title presentation** - Turok VR uses its own VR title presentation while leaving the original game content intact.
- **Controller reference layouts** - Dedicated control diagrams are available for both right-handed and left-handed configurations directly inside `VR Options > Controls`.
- **Pickup message placement** - Choose between `NORMAL`, `BOTTOM`, or `OFF`.
- **VR-scaled status messages** - Low Health, Low Armour, HUB Level Select, and training messages are enabled and scaled for VR.
- **Boss and Air bars** - Adds a VR-adjusted boss health bar and a low-air indicator while underwater.
- **Armour HUD support** - Armour is displayed on the wrist HUD alongside the existing status information.
- **Improved weapon wheel pointer** - Hand-pointer alignment has been adjusted for more accurate weapon-wheel interaction.
- **Version display** - The current Turok VR version is shown inside the VR Options menu.

## Haptic Feedback

Separate vibration controls are available for different types of interaction:

- **Weapons**
- **Damage**
- **Environmental effects**
- **Climbing**

Each category can be adjusted independently.


## OpenXR and Runtime Compatibility

- **OpenXR only** - Turok VR requires OpenXR and does not support Direct3D rendering.
- **Vulkan required** - The game must use the Vulkan graphics API for VR.
- **SteamVR and VDXR** - Both runtimes are supported.
- **Virtual Desktop support** - Virtual Desktop has been tested, with major VDXR-related performance issues and weapon-wheel problems addressed.

## Saving and Quicksaves

- **Quicksave and quickload** - Both are accessible while playing in VR.
- **Timestamped quicksaves** - Quicksaves include their creation date and time.
- **Continue from Main Menu** - A `Continue` option loads the latest quicksave directly from the Main Menu.
- **Improved final-boss quicksaves** - Additional handling improves quicksave behaviour during the final boss encounter.
- **VR state persistence** - VR-specific gameplay information such as shoulder weapon assignments is stored with the save game.
- **Bonus-level save handling** - Additional handling improves quicksave behaviour inside Turok's bonus areas.
- **Reliable VR configuration** - User configuration is preserved when reinstalling or updating the mod.

> **Quicksave warning:** Turok was not originally designed around unrestricted quicksaving. Although many situations have been tested and several known problems have been addressed, it is impossible to test every level state, scripted event, boss encounter, bonus area, or unusual gameplay situation. Quicksaving at unexpected moments may therefore cause unforeseen bugs or incorrect game states. Regular save points should still be used whenever possible.
