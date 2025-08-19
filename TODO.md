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

8. **Finalize my_post as standalone post-processing pass** - COMPLETED
   - Runs after final composite on its own pipeline
   - Does not interfere with FSR or NIS upscalers
