# Dear Imgui Sample using OpenTK

## OpenGL 3.3 details

This is a version of the sample meant for use with opengl 3.3, it is backported from a opengl 4.5 version and as such doesn't nessecarily contain the best and most optimized 3.3 code.

For example, there are a lot of uneccesary texture and buffer binds that could be taken out.

## BadImageFormatexception

If you get the following error you might have to set your platform target to x86:

```
System.BadImageFormatException: 'An attempt was made to load a program with an incorrect format. (Exception from HRESULT: 0x8007000B)'
```

To do that, right click your project (all projects referencing ImGui.NET), click "Properties", click "Build", and change the "Platform target" to "x86".

To see more info and a potential fix you can take a look at [issue #2](https://github.com/NogginBops/ImGui.NET_OpenTK_Sample/issues/2).

## Remember to enable/disable OpenGL features after use!

Note that `ImGuiController.Render()` enables and disables some OpenGL features. The following is a list of state that `ImGuiController.Render()` changes:

- Disbles blending
- Disables scissor test
- Disables culling
- Disables depth test
- Changes blend function
- Changes scissor rectangle
- Changes the shader program in use
- Sets texture unit `0`'s `Texture2D` to `zero`
- Sets blend equation to `FuncAdd`
- Sets blend func to `SrcAlpha`, `OneMinusSrcAlpha`
- Sets the `VertexArray` bound to zero
- Unbinds any Vertex Array Object