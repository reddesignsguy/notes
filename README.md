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
