# Foster.ImGUI

The famous ImGUI library ready to use in your Foster project!

## Installation

The easiest solution to add Foster.ImGUI into your project is using NuGeT: https://www.nuget.org/packages/FosterImGUI/1.0.1
```
dotnet add package FosterImGUI --version 1.0.1
```

Or you can install it by cloning the repository, adding the .csproj to your solution and adding it as a project reference.

## Usage

Firstly, you may instantiate a `Renderer`.
```csharp
public class MyGame : App
{
	Renderer _imGuiRenderer;

	public MyGame()
	{
		_imGuiRenderer = new(this);
	}
}
```
You can now build your ImGUI app inside the `Update`:
```csharp
protected override void Update()
{
	_imGuiRenderer.BeginLayout();

	// Put your ImGUI app here

	_imGuiRenderer.EndLayout();
}
```
Now, you only have to render everything!
```csharp
protected override void Render()
{
	Window.Clear(Color.Black);
	_imGuiRenderer.Render();
}
```
Don't forget to dispose the ImGui renderer at the `Shutdown` of your app!
```csharp
protected override void Shutdown()
{
	_imGuiRenderer.Dispose();
}
```
Enjoy!

## Credits

The code was taken from the [sample ImGUI project](https://github.com/FosterFramework/Samples/tree/app-refactor/ImGui) of [Noel](https://github.com/NoelFB)
The original library: https://github.com/ocornut/imgui
.Net wrapper of ImGUI: https://github.com/ImGuiNET/ImGui.NET