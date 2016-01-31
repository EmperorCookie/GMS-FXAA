# GMS-FXAA

A simple to use FXAA (Fast Approximate Anti Aliasing) shader for your project. It is based on NVIDIA's FXAA method and as a result is very efficient. Use it to replace the default Anti Aliasing method that comes with GameMaker:Studio.

For more details on FXAA, read [this Wikipedia article](http://en.wikipedia.org/wiki/Fast_approximate_anti-aliasing).

### Using the shader:

Included in the package is a premade object that does post processing effects in the simplest possible way with GameMaker:Studio. Just drop it in your project and it works.

### Alternate use:

Otherwise, to use the shader on something else than post processing, simply use it like this:

```
shader_set(sha_fxaa);
var tex = sprite_get_texture(sprite_index, image_index); // REPLACE THIS WITH THE SPRITE YOU WANT TO DRAW
shader_set_uniform_f(shader_get_uniform(sha_fxaa, "u_texel"), texture_get_texel_width(tex), texture_get_texel_height(tex));
shader_set_uniform_f(shader_get_uniform(sha_fxaa, "u_strength"), 4);
draw_self(); // REPLACE THIS WITH THE SPRITE YOU WANT TO DRAW
shader_reset();
```
### Patch Notes:

**1.1.0**

- Added a uniform to allow the strength of the effect to be changed
