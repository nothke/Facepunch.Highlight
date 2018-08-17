# Facepunch.Highlight
Mesh outline effect

![Preview](https://files.facepunch.com/garry/a0ad7775-03ac-49e4-83c0-b89301b6f64b.png)

# Usage

Add Highlighter.cs to your camera (or anywhere else and set the camera reference). There's some static functions that will make things easier if you're only using one type of outline.

```
        Highlight.ClearAll();
        Highlight.AddRenderer( HoveredRendererer );
        Highlight.AddRenderer( SomeOtherRendererer );
        Highlight.Rebuild();
```

Optimally you should only update the a highlighter when things change, not every frame, but it's not going to kill you if you do.

# Pros And Cons

Pros | Cons
-----|------
Can add multiple highlighters for different line colours/widths | Only one line colour/width per highlighter
Only costs perf when being used | Only works in deferred render mode
No need to add components to all your renderers | Needs depth texture generation on camera
Only re-renders the target objects | Transparent stuff won't occlude
Doesn't need to render potentially occluding objects | 
Can draw occluded lines a different colour |
Lines can glow and bloom by providing a HDR color |
Lines can get anti-aliased by post process |
You can edit the shader to do whatever you want |
Works on skinned meshes |
MIT license |

