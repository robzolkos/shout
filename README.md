# shout

Simple speech-to-text for Wayland/Hyprland. Press a key to record, press again to transcribe and press Enter.

Works great with AI coding agents like Claude Code - they're forgiving of typos and excellent at semantic reasoning, so transcription doesn't need to be perfect.



https://github.com/user-attachments/assets/3197004d-1f44-4433-872e-b5c14b28bda2



## Installation (Arch Linux / AUR)

```bash
yay -S shout
```

Uses the `tiny` whisper model (75 MB) - fastest transcription, good enough for AI agents.

## Setup

Add this keybind to `~/.config/hypr/hyprland.conf`:

```bash
bindd = SUPER, R, shout, exec, shout
```

Then reload: `hyprctl reload`

## Usage

1. Press `Super+R` to start recording
2. Speak
3. Press `Super+R` again to stop, transcribe, and type the text

## License

MIT
