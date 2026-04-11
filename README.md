# notes for myself but made public so i can show off lol

_**cmake**_
- add_subdirectory(subdir) -- used to reference and call another cmake project, where the subdir contains the CMakeLists.txt associated with said project
- find_package() -- looks for ".cmake" files
  - vcpkg used as a "cmake toolchain" to help find packages?
  - 2 modes:
    - CONFIG: Find<Package>.cmake
    - MODULE: <Package>Config.cmake
  - vcpkg must only be used on the top-level cmake directory
    - it is read before the first project() call
    - specify the vcpkg tool chain file "vcpkg.cmake" and do so via -DCMAKE_TOOLCHAIN_FILE flag
    - command: cmake -S . --build build -DCMAKE_TOOLCHAIN_FILE="etc"

- **_photoshop PSD spec_**
  - in the top left of Photopea, switching the drop down from path to shape doesn't do anything.
    - photoshop might treat both types of data the same internally
    - however, changing the color fill data does make a difference to the psd spec
  - Path Resource Format
    - Initial fill rule record (08)
    - The 2 bytes after the selector bytes, 00 08, are either 00 01 or 00 00. If it's 00 01, then it will "invert" the mask such that everything inside is hidden and everything outside is shown.
      - For some reason, I'm seeing this inversion at times for the resulting file of a round-trip write.
  - A shape's color fill depends on 8BIMSoCo or solid color thingy (listed in PSD spec)
    - Hex data with a RED solid color fill <img width="764" height="252" alt="image" src="https://github.com/user-attachments/assets/ce17c048-f617-4652-960f-202699d7be26" />

    - Hex data with a BLUE solid color fill (note the differences in highlighted cells) <img width="753" height="248" alt="image" src="https://github.com/user-attachments/assets/bd02fbe4-cc60-4ed8-bfd8-6d751bf4a6bd" />


