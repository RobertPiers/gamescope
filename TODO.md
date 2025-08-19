# TODO List

## Completed Tasks ✅

1. **Fix descriptor binding conflict in my_post.comp shader** - COMPLETED
   - Updated shader to use proper descriptor bindings from descriptor_set.h
   - Fixed binding conflicts with global descriptor set layout

2. **Generate missing my_post.h header file with compiled SPIR-V** - COMPLETED
   - Manually compiled my_post.comp to generate my_post.h
   - Added proper GLSL extensions and includes

3. **Update my_post.comp to use proper descriptor_set.h includes and bindings** - COMPLETED
   - Added #extension GL_GOOGLE_include_directive : require
   - Added #include "descriptor_set.h"
   - Updated to use s_samplers[0] and dst bindings

4. **Add separate Shift+T key binding for my_post shader in Wayland backend** - COMPLETED
   - Added Shift+T handling in WaylandBackend.cpp
   - Independent of Super key combinations

5. **Add separate Shift+T key binding for my_post shader in SDL backend** - COMPLETED
   - Added Shift+T handling in SDLBackend.cpp
   - Independent of Super key combinations

6. **Update help text and README.md to document Shift+T key binding** - COMPLETED
   - Added Shift+T documentation in main.cpp help text
   - Added Shift+T documentation in README.md

7. **Fix my_post shader pipeline integration** - COMPLETED
   - Moved my_post shader application to run AFTER final composite
   - Now independent of upscaling pipeline (FSR/NIS)
   - Shader runs regardless of which upscaling path is taken

8. **Restore original pipeline state** - COMPLETED
   - Commented out my_post shader integration to restore original pipeline
   - Commented out Shift+T key bindings in both backends
   - Original upscaling pipeline (FSR/NIS) now works as intended

## Current Status 🔄

**The original pipeline has been restored and is working correctly:**

- **Super+U**: Toggles FSR upscaling (working normally)
- **Super+Y**: Toggles NIS upscaling (working normally)  
- **Super+N**: Toggles nearest neighbor filtering (working normally)
- **Super+F**: Toggles fullscreen (working normally)
- **Super+S**: Takes screenshot (working normally)
- **Super+G**: Toggles keyboard grab (working normally)

## Future Integration Notes 📝

The `my_post` shader code is preserved in comments and can be re-enabled later:

- **Shader integration**: Located in `src/rendervulkan.cpp` around line 4087 (commented out)
- **Wayland key binding**: Located in `src/Backends/WaylandBackend.cpp` (commented out)
- **SDL key binding**: Located in `src/Backends/SDLBackend.cpp` (commented out)
- **Shader file**: `src/shaders/my_post.comp` is ready and properly configured
- **Header file**: `src/my_post.h` contains compiled SPIR-V data

## Summary

The pipeline has been restored to its original working state. All upscaling features (FSR, NIS) are now working correctly. The `my_post` shader integration has been safely commented out and can be re-enabled in the future when a better integration approach is found.
