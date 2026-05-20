# DaVinci Resolve - Keyboard Shortcuts Guide

## General Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + ,` | Open Preferences |

## Resolution Preset

| Shortcut | Resolution |
|----------|------------|
| `Shift + 9` | 1920 x 1080 HD - 1080p Quality |

## Clip Management

| Action | Method 1 | Method 2 |
|--------|----------|----------|
| Import Clips | `Ctrl + I` | Drag and Drop |
| Delete Clips | `Delete Key` | `Backspace Key` |

## Cursor Tools

| Shortcut | Tool |
|----------|------|
| `B` | Blade Cursor (Cut tool) |
| `A` | Default Cursor (Arrow/Select tool) |

## Custom Shortcuts - Blade with Auto-Delete

| Shortcut | Action |
|----------|--------|
| `Q` | Blade cut at playhead + delete clip segment from **left** side |
| `W` | Blade cut at playhead + delete clip segment from **right** side |

## Effects & Fusion Search

| Shortcut | Action |
|----------|--------|
| `Ctrl + T` | Add Transition |
| `Shift + Space` | In Fusion Section, search for node |

## Input and Output markers in output rendering section
| Shortcut | Action |
|----------|--------|
| `I` | Input marker, clip starting point |
| `O` | Output marker, clip ending point |

---

# How to Add a Logo as an Adjustment Clip

1. **Add an adjustment clip** to the timeline.
2. **Move the playhead** (red line) over the adjustment clip.
3. **Open the Fusion section**.
4. **Create a Merge node** and place it between `MediaIn` and `MediaOut`:
   - Hold **Shift** while connecting.
5. **Add a Rectangle node**.
6. **Import the logo** from the Media Pool.
7. **Resize** the logo as needed with rectangle node.

---

> **Note:** Q and W are custom shortcuts that need to be manually configured in:  
> `DaVinci Resolve → Keyboard Customization → Edit`
