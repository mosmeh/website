---
title: Projects
---

# Projects

## Low-level

### yagura

A Unix-like operating system for x86.\
[GitHub](https://github.com/mosmeh/yagura)

![](imgs/yagura.png)

### microcosm

A minimal KVM-based virtual machine monitor.\
[GitHub](https://github.com/mosmeh/microcosm)

### Bare-metal programs

Programs written for bare-metal environments.

- [x86-bare-metal-raytracer](https://github.com/mosmeh/x86-bare-metal-raytracer): [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html) on x86 bare-metal
- [x86-bare-metal-donut](https://github.com/mosmeh/x86-bare-metal-donut): [donut.c](https://www.a1k0n.net/2006/09/15/obfuscated-c-donut.html) on x86 bare-metal

## Programming language implementations

### mochi

Lua runtime implemented in Rust.\
[GitHub](https://github.com/mosmeh/mochi)

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

## Databases

### squalodon

An embedded relational database management system written from scratch.\
[GitHub](https://github.com/mosmeh/squalodon)

- SQL parser
- Planner
- Execution engine
- Join order optimization
- Pluggable storage backends

### qwerk

An embedded transactional key-value store.\
[GitHub](https://github.com/mosmeh/qwerk)

```rust
let db = Database::open("db")?;
let mut worker = db.worker()?;
let mut txn = worker.transaction();
txn.insert(b"key", b"value")?;
assert_eq!(txn.get(b"key")?, Some(b"value".as_slice()));
txn.commit()?;
```

  - ACID transactions with strict serializability
  - Optimized for multi-threaded workloads with multiple concurrent readers and writers
  - Persistence to the disk

### zakros

Redis-compatible in-memory database replicated with [Raft consensus algorithm](https://raft.github.io/).\
[GitHub](https://github.com/mosmeh/zakros)

### zseqd

A distributed monotonically increasing sequence generator.\
[GitHub](https://github.com/mosmeh/zseqd)

```sh {linenos=false}
> INCR myseq
(integer) 42
> INCR myseq
(integer) 43
```

## CLI tools

### indexa

A locate alternative with incremental search.\
[GitHub](https://github.com/mosmeh/indexa)

![](imgs/indexa.png)

Designed to utilize multiple CPU cores and minimize memory usage. \
Inspired by [Everything](https://www.voidtools.com/), which is another great file locator.

## Audio and synthesizers

### Web synthesizers and audio effects

Various synthesizers and effects utilizing WebAudio [AudioWorklet](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet).

![](imgs/syndx.png)

- [synks](https://mosmeh.github.io/synks/): Karplus-Strong string synthesizer
- [synxylo](https://mosmeh.github.io/synxylo/): Physical modeling xylophone synthesizer
- [syndx](https://mosmeh.github.io/syndx/): FM synthesizer for electric piano sound
- [syntw](https://mosmeh.github.io/syntw/): Tonewheel organ sound synthesizer
- [phaker](https://mosmeh.github.io/phaker/): Physically-based shaker sound synthesizer
- [forma](https://mosmeh.github.io/forma/): Formant filter
- [web-channel-eq](https://mosmeh.github.io/web-channel-eq/): Ableton Live's Channel EQ

### accent

Implementation of audio reverberation algorithms.\
[GitHub](https://github.com/mosmeh/accent)

### Synth Playground

Web playground to play with WebAudio [AudioWorklet](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet).\
[Try online](https://mosmeh.github.io/synth-playground/)
[GitHub](https://github.com/mosmeh/synth-playground)

![](imgs/synth-playground.png)

### primesynth

SoundFont-powered MIDI synthesizer.\
[GitHub](https://github.com/mosmeh/primesynth)

## Web

### Witchbooru

![](imgs/witchbooru.png)

[Try online](https://mosmeh.github.io/witchbooru/)

Image recognition system for anime characters. \
Trained with [Danbooru](https://danbooru.donmai.us/) data and built on top of [DeepDanbooru](https://github.com/KichangKim/DeepDanbooru) model. \
Deployed as an AWS Lambda function.

### beek

A modern REPL-style calculator.\
[GitHub](https://github.com/mosmeh/beek)

![](imgs/beek.png)

[Web version](https://mosmeh.github.io/beek/) is built with WebAssembly.

### Web services accessible from terminal

Web apps you can use via curl, wget, etc.

![](imgs/uclock.png)

- [twch](https://github.com/mosmeh/twch): Twitch chat viewer
- [uclock](https://github.com/mosmeh/uclock): Unix time clock

## Games

### TUI games

Games in text user interface.

![](imgs/yachtee.png)

- [fifteen](https://github.com/mosmeh/fifteen): The 15-puzzle
- [codebreaker](https://github.com/mosmeh/codebreaker): Mastermind
- [yachtee](https://github.com/mosmeh/yachtee): Yahtzee

### mahjongg

Mahjong solitaire game (aka Shanghai) compatible with [GNOME Mahjongg](https://wiki.gnome.org/Apps/Mahjongg) and [KMahjongg](https://games.kde.org/games/kmahjongg/).\
[GitHub](https://github.com/mosmeh/mahjongg)

![](imgs/mahjongg.png)

### mckalah

Monte Carlo tree search player for [Kalah](https://en.wikipedia.org/wiki/Kalah).\
[GitHub](https://github.com/mosmeh/mckalah)

## Text processing

### suffine

Suffix array construction tool/library for huge strings.\
[GitHub](https://github.com/mosmeh/suffine)

```rust
let text = "I scream, you scream, we all scream for ice cream!";
let index = IndexBuilder::new(text)
    .block_size(1024 * 1024)
    .build()
    .unwrap();
assert_eq!(index.positions("cream"), &[30, 44, 15, 3]);
```
