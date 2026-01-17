# zc_pong

## Description
This project serves as a practice of using only pure [Zen-C](https://github.com/z-libs/Zen-C) to compile and link against raylib to generate a wasm build of a simple pong game.

Check out the [Zen-C](https://github.com/z-libs/Zen-C) programming language here! Kudos to [Zuhaitz-dev](https://github.com/Zuhaitz-dev) for creating what I would call, [cppfront](https://github.com/hsutter/cppfront) of the C language.

## Game
Play it here [https://lamweilun.github.io/zc_pong](https://lamweilun.github.io/zc_pong)

Controls for the game: 
- W/S to control the left paddle
- I/K to control the right paddle

## Build Instructions
NOTE: Zen-C is still heavily in development. So far, built and tested on Linux using this specific [commit](https://github.com/z-libs/Zen-C/commit/f026d721ef6e1708b4ec28fdb68179cb7dda75d0) of Zen-C. But it should work with any newer versions of Zen-C.

1. Setup [emscripten](https://emscripten.org/docs/getting_started/downloads.html)
2. Setup [Zen-C](https://github.com/z-libs/Zen-C) compiler
3. Build raylib with emscripten, following the guide [here](https://github.com/raysan5/raylib/wiki/Working-for-Web-(HTML5)) from raylib's repo
4. Clone this repo
5. Create a folder named `external` in the root, and create a `raylib` folder in it.
6. Place a Web version of `libraylib.a` and raylib's `include` folder inside the `raylib` folder
    - It should look like this
      - `zc_pong/external/raylib/include/raylib.h`
      - `zc_pong/external/raylib/include/raymath.h`
      - `zc_pong/external/raylib/libraylib.a`
7. Modify any code in `main.zc` as you see fit
8. Build with the following commands...
    - Use this if you want to use emscripten's html
      - `zc build main.zc --cc emcc -o main.html`
    - Use this if you want to just update the JS and WASM file, maintaining the provided HTML file
      - `zc build main.zc --cc emcc -o main.js`
