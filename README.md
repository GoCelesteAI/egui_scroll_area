# Log Viewer — egui Scroll Area

Episode 10 of the **Learn egui in Neovim** series.

A log viewer app that displays a scrollable list of log entries and automatically scrolls to the bottom when new entries are added.

## What You'll Learn

- `egui::ScrollArea::vertical()` to make content scrollable
- `stick_to_bottom(true)` to auto-scroll as new entries arrive
- Adding items to a `Vec` and rendering them in a scroll area
- Building live-updating list UIs

## Run

```bash
cargo run
```

## Key Code

```rust
egui::ScrollArea::vertical()
    .stick_to_bottom(true)
    .show(ui, |ui| {
        for (i, log) in self.logs.iter().enumerate() {
            ui.label(format!("[{}] {}", i + 1, log));
        }
    });

if ui.button("Add Log Entry").clicked() {
    self.next_id += 1;
    self.logs.push(format!("Event #{}", self.next_id));
}
```

## Series

This is part of the [Learn egui in Neovim](https://www.youtube.com/@CelesteAI) series, where we build Rust GUI apps step by step.
