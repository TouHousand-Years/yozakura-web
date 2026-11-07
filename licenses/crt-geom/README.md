# CRT_Geom

Source: https://github.com/libretro/common-shaders/blob/master/crt/shaders/crt-geom.cg

Copyright (C) 2010-2012 cgwg, Themaister and DOLLS.
Licensed under GPL version 2 or, at your option, any later version.
The upstream shader is included as `crt-geom.cg`; the license is `COPYING.txt`.

The GLSL ES port in `src/ui/crt-geom.ts` preserves linear-light Lanczos2
reconstruction, the non-Gaussian beam profile, three-tap beam oversampling,
CRT gamma 2.4, and monitor gamma 2.2. The green/magenta dot mask (0.3)
is applied in `src/ui/retro-renderer.ts` after the other effects. The beam
profile and dot mask both run at physical output resolution. The intensity
control blends from the unfiltered image.

Project adaptations: progressive 853x480 input (no alternating interlace),
no overscan or rounded-corner cropping, and upstream curvature disabled.
The existing independently controlled barrel displacement supplies curvature
and shares its coordinate map with pointer hit testing.

Manual verification: enable CRT_Geom with barrel disabled, adjust intensity
from 0 to 100, then combine with barrel, bloom and glitch. Check text, animation,
scrolling, pointer alignment, window resizing and high-DPI output. Disable the
filter and verify that the original display returns; restart to check persistence.
