GHOST CURSOR

A small Python script that moves the mouse cursor to a random position on screen every second, to prevent the system from going idle. Press **Esc** at any time to stop it.

## How it works

- A background thread continuously moves the mouse to a random `(x, y)` coordinate within the screen bounds once per second, printing the new position to the console.
- A keyboard listener runs alongside it, watching for the **Esc** key. Pressing it sets a shared `running` flag to `False`, which stops the movement loop and ends the listener.

## Requirements

- Python 3.7+
- [`pynput`](https://pypi.org/project/pynput/)

Install the dependency:

```bash
pip install pynput
```

## Usage

1. Update `screen_width` and `screen_height` in the script if your screen resolution isn't 1920x1080.
2. Run the script:

   ```bash
   python mouse_jiggler.py
   ```
3. The console will print each new mouse position once per second.
4. Press **Esc** to stop the script (kill switch).

## Notes

- On macOS, you may need to grant the terminal/IDE **Accessibility** permissions (System Settings → Privacy & Security → Accessibility) for `pynput` to control the mouse and listen for key presses.
- On Linux, this requires an X11 session; it won't work out of the box under Wayland without extra configuration.
- Moving the mouse randomly will interrupt anything you're actively doing with it — don't run this while you need to use the mouse for other work.
- If you're using this to keep a status indicator "active" on a work or school system, check your organization's policies first — some consider this a violation of acceptable-use rules.

## License

Use and modify freely.
