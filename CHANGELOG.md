# Turok VR Changelog

This changelog is a cleaned-up version of the original development notes. Items are grouped by development phase and topic for readability.

## Development Phase 6 - 2026-09-17

### HUD and VR Options

- Fixed the **Classic HUD** being incorrectly positioned and mirrored in left-handed mode.
- Enabled the **Y button** as **Back** inside the VR Options menus.

### Weapons and Support Hand

- Recalibrated and optimized the proximity zones used for attaching the off hand to weapons.
- Added **Trigger-based support-hand attachment**:
  - Hold Trigger to attach the off hand to a compatible weapon.
  - Release Trigger to detach it again.
  - Normal Trigger weapon switching is temporarily disabled while the support hand is attached.
- The attached off hand can now also influence and move the weapon, making two-handed handling feel more natural.
- Fixed a weapon-state issue when switching between the **Tomahawk / Knife** and the **Bow**, where the weapon state could incorrectly reset to `0`.

### Immersive Climbing

- Added wall collision checks to immersive climbing.
- Increased the release/fall threshold slightly so the player does not need to re-grab the wall as quickly during immersive climbing.

---

## Development Phase 5 - 2026-09-02

### Visuals and Rendering

- Added new toggle **classic** in HUD-Options
  - ON (hand-mounted HUD), CLASSIC (a smaller, head-locked version of the original HUD, and OFF
- Added a new **Draw Distance** option under **VR Options > Visuals**.
  - `DEFAULT` uses the original `1x` draw distance.
  - Additional levels increase draw distance from `2x` through `7x`.
  - `MAX` uses `8x`, extending visibility beyond the game's normally allowed range.
  - Higher values can cause reduced performance or unexpected rendering/gameplay issues and should be used with caution.
- Updated the default color settings:
  - Saturation: `1.40`
  - Contrast: `1.05`
  - Brightness: `-0.06`
- Updated **Color Defaults** so the reset option restores the new values above.
- Added and refined VR scaling for status messages, including:
  - Low Health
  - Low Armour
  - Level Select messages in the HUB
  - Training level messages
- Added on-screen **Boss Health** and **Air** bars.
  - Boss health is shown during boss encounters.
  - The air bar appears when oxygen is running low underwater.
- Reduced the size of the boss health bar and moved it slightly lower on screen.
- Fixed clipped HUD pixels.
- Added Armour to the wrist HUD.
- Fixed Health and Armour icons being swapped while Armour was active.
- Moved the special-ammunition indicator upward for better readability.
- Added a confirmation sound when switching special ammunition.
- Added a new **Pickup Messages** option:
  - `NORMAL`
  - `BOTTOM`
  - `OFF`
- Further adjusted the cheat menu for VR.
- Moved the Options menu slightly upward for improved headset positioning.

### Movement, Turning and Comfort

- Added **Turn Speed** for smooth turning:
  - `FAST`
  - `MEDIUM`
  - `SLOW`
- `MEDIUM` is the default turn speed.
- The Turn Speed option is disabled when Snap Turning is selected.
- Disabled the small forced camera movement that could occur when exiting a climb.
- Fixed the off hand remaining too high while crouching.
- Fixed the off hand jumping upward when landing after a jump.
- Reworked the off-hand movement foundation to improve stability while moving and changing direction.
- Fixed initial off-hand positioning when starting or loading into a game.
- Improved off-hand persistence between game sections where the hand could previously disappear.

### Weapons and Hands

- Added **Hide HUD on Immersive Grip** under **VR Options > Weapons**.
  - Enabled by default.
  - Hides the wrist HUD while the immersive support-hand grip is active.
- Improved hand orientation and calibration.
- Added a hand-rotation calibration tool and recalibrated hand orientation.
- Further tuned the support-hand attachment area around weapons.
- Extended the usable forward attachment region while reducing accidental attachment near the weapon.
- Made support-hand detachment easier and more reliable.
- Mirrored weapon-hand models for left-handed mode.
- Re-enabled immersive support-hand attachment for left-handed players using the newly mirrored hand/weapon setup.
- Automatically hide the weapon, off hand, and wrist HUD while the Pause Menu is open.
- Hide hands during cutscenes.
- Re-aligned the hand pointer used by the weapon wheel.
- Hide the currently equipped weapon while the weapon wheel is open.

### Tomahawk

- Added the **Tomahawk** as a selectable weapon.
- Added a dedicated Tomahawk model and hand setup.
- Calibrated the Tomahawk position for VR.
- Added Tomahawk support to weapon selection using Trigger and Grip controls.
- Added a dedicated Tomahawk HUD icon.
- Added Tomahawk selection through the off hand using Grip while pointing at the knife entry.

### Saves and Game Flow

- Added **Continue** to the Main Menu for loading the latest quicksave.
- Updated the quicksave display so the creation date/time is shown instead of the generic loading label.
- Improved quicksave handling during the final boss encounter.
- Continued improving edge cases around quicksave restoration.

### Menus and Startup

- Added startup validation for important VR settings.
  - Incorrect startup settings can trigger an automatic restart with compatible values.
  - This includes incompatible aspect-ratio/resolution settings and enabled startup videos.
- Fixed the default 16:9 resolution on first launch.
- Disabled the three original startup videos in VR because they are not displayed correctly through OpenXR.
- Added the Turok VR version number to the VR Options menu.
- Updated and tested release default values.
- Added and refreshed controller reference images both in the release and inside **VR Options > Controls**.
- Added the complete controller layout to the README.
- Added the weapon pivot to `TurokVR-WAFFEN-KALIBRIERUNG.cmd` for easier calibration.
- Rechecked weapon calibration across the current release.

### OpenXR, Virtual Desktop and Compatibility

- Added a clear warning that **Vulkan is required for VR**.
  - Direct3D is not supported by Turok VR.
  - If Direct3D was selected previously, Turok must be launched in desktop mode and switched back to Vulkan before starting the VR mod.
- Added the Vulkan requirement to both the README and installation documentation.
- Tested Virtual Desktop support.
- Fixed most of the previously observed VDXR / Virtual Desktop performance issues.
- Fixed the weapon wheel under VDXR.
- Added warnings related to Virtual Desktop SSW where relevant in the documentation.
- Updated installation and Markdown documentation for the current release.

### Release and Documentation

- Added controller images under the README media files.
- Added the **Weapon Camera Shake** option to the README.
- Added the controller bindings to the README.
- Added a warning about the current water-reflection artifacts.
- Updated the feature list.
- Audited the complete release structure, including subfolders, to verify that all required files are included.
- Updated installation notes and release documentation.

### Existing Features Finalized for This Phase

- **Knife Mode: BOTH** is now the default.
  - Trigger input uses the classic automatic knife attack.
  - Physical controller swings use immersive melee.
- **Climbing Mode: BOTH** is now the default.
  - Normal automatic climbing remains available.
  - Grabbing the wall during a normal climb switches directly into immersive climbing.
- Further refined left-hand weapon attachment and release behavior.
- Continued calibration of weapon positions and beam alignment.

---

## Development Phase 4 - 2026-08-09

### Release and Documentation

- Added a recommendation for the [iddqd_textures](https://www.moddb.com/mods/iddqd-textures/addons/iddqd) texture pack.
- Added documentation explaining Turok's internal 60 Hz game logic and higher OpenXR display refresh rates.
- Added OpenXR requirements and SteamVR setup instructions.
- Added VDXR support information to the installation notes.
- Added warnings explaining that this is a complex reverse-engineered VR mod and that some features, especially immersive climbing, may still be imperfect.
- Prepared the first private GitHub release.
- Cleaned up the release package.
- Created a GitHub repository for issue tracking and development.

### Weapons and Hands

- Rebuilt the weapon models for VR.
- Completed or replaced original weapon models that were too incomplete for free VR viewing.
- Added all required hand switching behavior to supported weapons.
- The bow now hides the tracked left hand because the bow model already includes a hand holding the grip.
- Added configurable weapon hand display modes:
  - `NONE`
  - `BOTH`
  - `RIGHT`
  - `IMMERSIVE`
- Added an optional off-hand toggle.
- Completed and tested left-handed weapon handling.
- Bound the GUI/HUD to the appropriate off hand in left-handed mode.
- Tested immersive support-hand behavior in left-handed mode.
- Corrected knife position and orientation.
- Corrected knife orientation while swimming.
- Removed the original hand from the knife model and corrected its origin.
- Disabled the knife walking animation.
- Enabled the knife swing animation when immersive knife behavior is not active.
- Improved weapon placement after selecting a weapon.
- Added a weapon sway toggle for movement.

### Climbing

- Further improved immersive climbing.
- Added HD climbing hands.
- Weapons are hidden while climbing and the climbing hands are shown instead.
- Fixed the Climb Auto Lock option.
- Improved climbing transitions and interaction behavior.

### Controls and UI

- Added right-handed and left-handed controller reference graphics.
- Added controller graphics directly to **VR Options > Controls**.
- Fixed the Back button so it remains available throughout the options menus.
- Changed the HUD scale option to a simple `ON/OFF` toggle.
- Realigned the cheat menu for VR.
- Reduced the size of the pause menu for better VR readability.
- Improved weapon wheel thumbnails.
- Set **Adjust View to Slopes** to default `OFF` and disabled the original conflicting main-menu setting.
- Added separate rumble strength controls for:
  - Weapons
  - Environment
  - Climbing
  - Damage
- Added optional diagnostic logging through:

```ini
[Diagnostics]
ActivateLogs=1
```

### Rendering and Performance

- Fixed HMD orientation at startup.
- Resolved major framerate and movement judder problems.
- Improved overall smoothness during movement.
- Consolidated VR assets into `mods\\zzzz_VR_Assets.kpf`.
- Integrated the old `TurokVR.ini` and `TurokVRControls.ini` settings into the DLL and `TurokVRUser.ini`.
- Embedded the Turok VR title image resource inside the DLL.

---

## Development Phase 3

### Weapon Wheel and Shoulder Slots

- Removed the separate shoulder-slot assignment menu entry.
- Shoulder weapons are now configured directly from the weapon wheel.
- Pressing the **Left Trigger** while selecting a weapon assigns it to the left shoulder slot.
- Pressing the **Right Trigger** assigns it to the right shoulder slot.
- The weapon wheel displays an `L` or `R` marker for assigned shoulder weapons.
- Shoulder-slot assignments are stored in the save game.

---

## Development Phase 2

### Immersive Climbing

- Improved immersive climbing and weapon-position reset behavior.
- Added immersive wall climbing using Grip or Trigger.
- Added two climbing styles:
  - Normal physical climbing
  - Faster climbing through stronger upward controller movement
- Added the option to disable immersive climbing.

### Saves and Quicksaves

- Fixed quicksaves in bonus levels.
- Moved VR quicksave position data into the save-game folder.
- Added date and time information to quicksaves.
- Prevented `TurokVRUser.ini` from being overwritten during reinstallations.

### VR Options and Menus

- Re-enabled Video Options.
- Disabled or greyed out settings that should not be changed in VR.
- Added VR-specific resolution presets with apply-and-restart behavior.
- Reorganized options into clearer VR-specific sections.
- Added comfort vignette levels:
  - `OFF`
  - `WEAK`
  - `MEDIUM`
  - `STRONG`
- Moved VR Options into the main Options menu.
- Replaced the original Input section with the VR controls interface.
- Added a new crosshair menu with:
  - On/Off
  - Size
  - Color

### Rendering

- Re-enabled water reflections in Graphics Options but kept them disabled by default.
- Repaired the water reflection shader for VR.
- Fixed GUI elements that previously appeared in only one eye.
- Improved frame pacing and added a recommendation for 120 Hz where supported.
- Embedded the Turok VR title graphic in the DLL and injected it into the renderer.

### Weapons and Aiming

- Added **Alternate Ammo** to the VR bindings.
- Improved bow aiming and corrected bow rotation behavior.
- Improved weapon aiming so it aligns consistently with the crosshair.
- Improved knife melee.
- Disabled muzzle flashes because the original effect could not be aligned reliably with the VR weapon pivots.
- Position Reset now also resets weapon position.
- Reworked the crosshair into a convergent, collision-aware world-space crosshair that stays in front of world geometry.

### Installation and Reliability

- Added `steam_appid.txt` handling so renamed Turok installation folders can still launch correctly.
- Preserved `TurokVRUser.ini` across reinstallations.

---

## Development Phase 1

### Installation

- Added automatic extraction of the OpenXR DLL and VR assets.
- Added an uninstaller.
- Added automatic installation from the `turok.assets` archive.
- Configured VR defaults on first start.
- Disabled the splash movie by default.
- Set water reflections to `OFF` and refraction to `ON` by default.

### Rendering and Menus

- Improved the water shader.
- Stabilized the desktop mirror and switched it to a left-eye view.
- Reduced menu scale for VR.
- Removed incompatible Video and Input options from the VR menus at this stage of development.
- Improved menu pointer alignment.

### Weapons and Aiming

- Added quicksave and quickload.
- Improved arrow accuracy and bow rotation.
- Improved crosshair aiming.
- Improved weapon movement and wrist attachment.
- Added options for automatic horizon/view adjustment on slopes and while swimming.
- Attached the weapon wheel to the hand.
- Added slow motion while the weapon wheel is open.
- Disabled movement and firing while selecting a weapon.
- Added shoulder weapon configuration through gestures.
- Removed traditional gun recoil.
- Added options for head bobbing and recoil behavior.
- Increased the shoulder-slot delay to 500 ms while the knife is equipped to avoid accidental activation.

### Project

- Added Git source control.

---

## Early Development

### Core VR

- Added true VR rendering instead of a virtual flat screen.
- Added stereoscopic 3D.
- Added full 6DoF head tracking.
- Added 6DoF motion-controlled weapons.
- Added OpenXR support using the Vulkan renderer.
- Added roomscale movement.
- Added head-oriented movement direction.
- Added smooth analog locomotion instead of the original digital-style movement.
- Disabled traditional head bobbing for VR comfort.
- Corrected lighting issues that appeared when tilting the head.

### Weapons

- Added the weapon wheel.
- Added physical knife melee.
- Added adjustable knife swing velocity.
- Added shoulder gestures for quickly drawing the knife and bow.
- Began completing original weapon meshes for full VR viewing.
- Replaced the original crosshair behavior with a VR-compatible solution.

### Controls and UI

- Added a position reset control.
- Added a crouch button.
- Added left-handed mode.
- Added a dedicated VR menu.
- Added smooth and snap turning.
- Added configurable controller bindings.
- Added a VR mouse/pointer for menus.
- Added headset-relative menu positioning.
- Added UI visibility controls.
- Added UI size controls.
- Added brightness, contrast, saturation, and color adjustment options.
- Bound the UI/HUD to the left hand.

### Haptics

- Added rumble feedback for:
  - Damage
  - Weapon attacks
  - Environmental vibration events
  - Other gameplay interactions
