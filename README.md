# shout

Simple speech-to-text for Wayland/Hyprland. Press a key to record, press again to transcribe and press Enter.

Works great with AI coding agents like Claude Code - they're forgiving of typos and excellent at semantic reasoning, so transcription doesn't need to be perfect.



https://github.com/user-attachments/assets/3197004d-1f44-4433-872e-b5c14b28bda2



## Installation (Arch Linux / AUR)

**Prerequisite:** A Vulkan driver for your GPU (install one):
```bash
# AMD (often pre-installed)
sudo pacman -S vulkan-radeon

# Intel
sudo pacman -S vulkan-intel

# NVIDIA (usually comes with nvidia drivers)
sudo pacman -S nvidia-utils

# No GPU / fallback (slower)
sudo pacman -S vulkan-swrast
```

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

## Troubleshooting

### File conflicts with libggml-git

If you see errors like `libggml-git: /usr/include/ggml.h exists in filesystem (owned by whisper.cpp)`:

```bash
# Remove old whisper.cpp that bundles ggml
yay -Rns whisper.cpp

# Fresh install
yay -S shout
```

This happens when upgrading from an older whisper.cpp that bundled ggml internally.

## License

MIT
