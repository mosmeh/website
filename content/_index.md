---
layout: single
---

# **Yuta Imazu**

I'm a software engineer living in Tokyo, Japan. \
Among many other things, I'm fascinated by command-line apps, database systems, distributed systems, and synthesizers.

# Projects

## [indexa](https://github.com/mosmeh/indexa)

A locate alternative with incremental search.

![](imgs/indexa.png)

Designed to utilize multiple CPU cores and minimize memory usage. \
Inspired by [Everything](https://www.voidtools.com/), which is another great file locator.

## Bare-metal programs

Programs written for bare-metal environments.

![](imgs/yagura.png)

-   [yagura](https://github.com/mosmeh/yagura): A Unix-like operating system for x86
-   [x86-bare-metal-raytracer](https://github.com/mosmeh/x86-bare-metal-raytracer): [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html) on x86 bare-metal
-   [x86-bare-metal-donut](https://github.com/mosmeh/x86-bare-metal-donut): [donut.c](https://www.a1k0n.net/2006/09/15/obfuscated-c-donut.html) on x86 bare-metal

## [mochi](https://github.com/mosmeh/mochi)

Lua runtime implemented in Rust.

```lua
local function factorial(n)
    if n == 0 then
        return 1
    else
        return n * factorial(n - 1)
    end
end

local n = tonumber(arg[1] or 10)
print(n .. "! = " .. factorial(n))
```

```sh {linenos=false}
$ mochi factorial.lua 12
12! = 479001600
```

 - Bytecode VM compatible with PUC-Rio Lua 5.4
 - Lexer and parser
 - AST to bytecode compiler
 - Incremental mark-and-sweep garbage collection
 - Standard library implementation

## [zakros](https://github.com/mosmeh/zakros)

Redis-compatible in-memory database replicated with [Raft consensus algorithm](https://raft.github.io/). \
Enjoy strong consistency provided by Raft with familiar Redis interface!

## Web synthesizers & audio effects

Various synthesizers and effects utilizing WebAudio [AudioWorklet](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet).

![](imgs/syndx.png)

-   [synks](https://mosmeh.github.io/synks/): Karplus-Strong string synthesizer
-   [synxylo](https://mosmeh.github.io/synxylo/): Physical modeling xylophone synthesizer
-   [syndx](https://mosmeh.github.io/syndx/): FM synthesizer for electric piano sound
-   [syntw](https://mosmeh.github.io/syntw/): Tonewheel organ sound synthesizer
-   [phaker](https://mosmeh.github.io/phaker/): Physically-based shaker sound synthesizer
-   [forma](https://mosmeh.github.io/forma/): Formant filter
-   [web-channel-eq](https://mosmeh.github.io/web-channel-eq/): Ableton Live's Channel EQ

## [Witchbooru](https://mosmeh.github.io/witchbooru/)

![](imgs/witchbooru.png)

Image recognition system for anime characters. \
Trained with [Danbooru](https://danbooru.donmai.us/) data and built on top of [DeepDanbooru](https://github.com/KichangKim/DeepDanbooru) model. \
Deployed as an AWS Lambda function.

## [beek](https://github.com/mosmeh/beek)

A modern REPL-style calculator.

![](imgs/beek.png)

[Web version](https://mosmeh.github.io/beek/) is built with WebAssembly.

## [accent](https://github.com/mosmeh/accent)

Implementation of audio reverberation algorithms.

## [Synth Playground](https://mosmeh.github.io/synth-playground/)

Web playground to play with WebAudio [AudioWorklet](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet).

![](imgs/synth-playground.png)

## Web services accessible from terminal

Web apps you can use via curl, wget, etc.

![](imgs/uclock.png)

-   [twch](https://github.com/mosmeh/twch): Twitch chat viewer
-   [uclock](https://github.com/mosmeh/uclock): Unix time clock

## [primesynth](https://github.com/mosmeh/primesynth)

SoundFont-powered MIDI synthesizer.

## TUI games

Games in text user interface.

![](imgs/yachtee.png)

-   [fifteen](https://github.com/mosmeh/fifteen): The 15-puzzle
-   [codebreaker](https://github.com/mosmeh/codebreaker): Mastermind
-   [yachtee](https://github.com/mosmeh/yachtee): Yahtzee

## [mahjongg](https://github.com/mosmeh/mahjongg)

Mahjong solitaire game (aka Shanghai) compatible with [GNOME Mahjongg](https://wiki.gnome.org/Apps/Mahjongg) and [KMahjongg](https://games.kde.org/games/kmahjongg/).

![](imgs/mahjongg.png)

## [mckalah](https://github.com/mosmeh/mckalah)

Monte Carlo tree search player for [Kalah](https://en.wikipedia.org/wiki/Kalah).

## [suffine](https://github.com/mosmeh/suffine)

Suffix array construction tool/library for huge strings.
