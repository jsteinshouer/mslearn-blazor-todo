
# Blazor ToDo App

[Razor Syntax Reference](https://learn.microsoft.com/en-us/aspnet/core/mvc/views/razor?view=aspnetcore-8.0)

[Blazor Sample Apps](https://github.com/dotnet/blazor-samples)

### Handling events

Use `@on<event>`

```html
<button class="btn btn-primary" @onclick="() => currentCount++">Click me</button>
```

```html
<input @onchange="InputChanged" />
<p>@message</p>

@code {
    string message = "";

    void InputChanged(ChangeEventArgs e)
    {
        message = (string)e.Value;
    }
}
```

### Data binding

```html
<input @bind="text" />
<button @onclick="() => text = string.Empty">Clear</button>
<p>@text</p>

@code {
    string text = "";
}
```

### Interactive mode

Rendering on the server over websockets

```
@rendermode InteractiveServer
```

Use `InteractiveWebAssembly` to render from the client.

### Todo list page

```bash
mkdir BlazorToDo
cd BlazorToDo
dotnet new blazor
```

```bash
dotnet new razorcomponent -n Todo -o Components/Pages
```