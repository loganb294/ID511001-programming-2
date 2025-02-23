# 10: Key Events

## Key Events

Key events are used to handle keyboard input in Windows Forms applications. The `KeyDown`, `KeyUp`, and `KeyPress` events are used to handle key events. The `KeyDown` and `KeyUp` events are used to handle key presses, while the `KeyPress` event is used to handle character input.

### Create Key Event Handlers

To create a key event handler, you need to go to the form's properties and select the `Events` tab. From there, you can select the `KeyDown` or `KeyUp` event and create an event handler.

### Enabling Key Events

To enable key events in a Windows Forms application, you need to set the `KeyPreview` property of the form to `true`. This property determines whether the form receives key events before the event is passed to the control that has focus.

```csharp
public Form1()
{
    InitializeComponent();
    KeyPreview = true;
}
```

### KeyDown and KeyUp Event

The `KeyDown` and `KeyUp` events are used to handle key presses. The `KeyDown` event is raised when a key is pressed, and the `KeyUp` event is raised when a key is released. These events provide information about the key that was pressed or released.

Here is an example of handling the `KeyDown` event:

```csharp
private void Form1_KeyDown(object sender, KeyEventArgs e)
{
    if (e.KeyCode == Keys.Space)
    {
        MessageBox.Show("Space key pressed!");
    }
}
```

Here is an example of handling the `KeyUp` event:

```csharp
private void Form1_KeyUp(object sender, KeyEventArgs e)
{
    if (e.KeyCode == Keys.Enter)
    {
        MessageBox.Show("Enter key released!");
    }
}
```

### Modifiers

The `KeyEventArgs` class provides properties to check for modifier keys such as `Alt`, `Control`, and `Shift`. You can use these properties to check if a modifier key was pressed along with the main key.

Here is an example of checking for modifier keys:

```csharp
private void Form1_KeyDown(object sender, KeyEventArgs e)
{
    if (e.KeyCode == Keys.Space && e.Control)
    {
        MessageBox.Show("Ctrl + Space key pressed!");
    }
}
```

**Note:** When testing, you need to press the `Ctrl` key first and then press the `Space` key to trigger the event.

### Handling Multiple Key Presses

You can use a `switch` statement to handle multiple key presses in the `KeyDown` event. This allows you to execute different code based on the key that was pressed.

Here is an example of using a `switch` statement:

```csharp
private void Form1_KeyDown(object sender, KeyEventArgs e)
{
    switch (e.KeyCode)
    {
        case Keys.A:
            MessageBox.Show("A key pressed!");
            break;
        case Keys.B:
            MessageBox.Show("B key pressed!");
            break;
        case Keys.Right:
            pictureBox1.Left += 10;
            break;
        case Keys.Left:
            pictureBox1.Left -= 10;
            break;
        default:
            MessageBox.Show("Other key pressed!");
            break;
    }
}
```

### KeyPress Event

The `KeyPress` event is used to handle character input. This event is raised when a character key is pressed. The `KeyPress` event provides information about the character that was pressed.

Here is an example of handling the `KeyPress` event:

```csharp
private void Form1_KeyPress(object sender, KeyPressEventArgs e)
{
    if (e.KeyChar == 'a')
    {
        MessageBox.Show("The 'a' key was pressed!");
    }
}
```

# Formative Assessment

No formative assessment provided in this topic.
