# Upaya
> upaya: a means that goes or brings one up to some goal; skillful means

Zig-based framework for creating game tools and helper apps. Consists of the following:
- *Sokol*: used for cross-platform window creation and rendering
- *STB Image*: image loader
- *Tiny Filebrowser*: cross-platform filebrowsers and dialogs
- *Dear ImGui*: needs no introduction

Upaya provides a set of conveniences to speed up tool building:
- *upaya.fs*: one-liners for saving/loading JSON/binary files
- *upaya.mem*: C allocator and a temp allocator (just use and never free)
- *upaya.menu*: helpers for managing a main menu bar
- *upaya.colors*: ImGui color translations and helpers
- *upaya.math*: math helpers and a random number generator

## Getting Started
First fetch Upaya: `git clone --recursive https://github.com/prime31/zig-upaya/`

Zig is a fast moving target right now and Upaya uses some of the newer features in the language. You will want to be using a [nightly build](https://ziglang.org/download/) of Zig rather than an older release. Once you have zig installed, you can use `zig build help`. The available examples will be listed in the `Steps` section. `zig build run` will always build the most recent example.

## Your First Upaya App
A full basic Upaya app is below. You can start putting code right in the `update` method which will be called each frame.
```zig
const upaya = @import("upaya");
usingnamespace upaya.imgui;

pub fn main() !void {
    upaya.run(.{
        .init = init,
        .update = update,
    });
}

fn init() void {}

fn update() void {
    _ = igBegin("My First Window", null, ImGuiWindowFlags_None);
    igEnd();
}
```
