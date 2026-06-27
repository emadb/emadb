defended earth since 1978<div align="center">

<pre>
00000000  65 6d 61 64 62 20 3a 3a  20 6c 6f 77 5f 6c 65 76  |emadb :: low_lev|
00000010  65 6c 20 65 6e 67 69 6e  65 65 72 0a 00 c0 ff ee  |el engineer.....|
00000020  72 75 73 74 c3 1f 80 80  85 80 0a de ad be ef 00  |rust............|
</pre>

<pre>
███████╗███╗   ███╗ █████╗ ██████╗ ██████╗ 
██╔════╝████╗ ████║██╔══██╗██╔══██╗██╔══██╗
█████╗  ██╔████╔██║███████║██║  ██║██████╔╝
██╔══╝  ██║╚██╔╝██║██╔══██║██║  ██║██╔══██╗
███████╗██║ ╚═╝ ██║██║  ██║██████╔╝██████╔╝
╚══════╝╚═╝     ╚═╝╚═╝  ╚═╝╚═════╝ ╚═════╝ 
</pre>

`; 01010010 01010101 01010011 01010100 — 4 bytes, big-endian, you figure it out`

<a href="https://github.com/emadb">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=16&pause=800&color=5FFF5F&center=true&vCenter=true&width=680&height=48&lines=%23!%5Bno_std%5D;unsafe+%7B+*(0xC000+as+*mut+u8)+%3D+self+%7D;0xC3+0x07+0x00+++%3B+jmp+.loop+(forever);fn+main()+-%3E+!+%7B+emulate(); defend_earth() %7D" alt="cryptic marquee" />
</a>

<br/>

[![Website](https://img.shields.io/badge/0x57-emanueledelbono.it-5FFF5F?style=for-the-badge&logo=google-chrome&logoColor=5FFF5F&labelColor=000000&color=000000)](http://emanueledelbono.it)
[![Bluesky](https://img.shields.io/badge/0x42-@emadb-5FFF5F?style=for-the-badge&logo=bluesky&logoColor=5FFF5F&labelColor=000000&color=000000)](https://bsky.app/profile/emadb.bsky.social)
[![Blog](https://img.shields.io/badge/0x52-PlasticBlog-5FFF5F?style=for-the-badge&logo=rss&logoColor=5FFF5F&labelColor=000000&color=000000)](https://blog.codiceplastico.com)

`👾   01000101   👾   01001101   🛸   01000001   👾   01000100   👾   01000010   👾`

</div>

<br/>

### `SPRITE_ROM[0x00] // invader.squid` — 8×8, the only sprite that matters

<pre>
   ██        db $18    0b00011000
  ████       db $3C    0b00111100
 ██████      db $7E    0b01111110     ; this is me, stored in 8 bytes
██ ██ ██     db $DB    0b11011011     ; defended earth since 1978
████████     db $FF    0b11111111
 █ ██ █      db $5A    0b01011010
█      █     db $81    0b10000001
 █    █      db $42    0b01000010
</pre>

<br/>

### `0x0000 RESET_VECTOR` — cold boot

```rust
#![no_std]
#![allow(human::needs_coffee)]

/// A low-level engineer. Emulates dead CPUs for fun, ships weird web apps for a living.
pub struct Emadb;

impl Machine for Emadb {
    const ROLE:     &str = "software engineer · co-founder @ CodicePlastico";
    const BASE:     &str = "Brescia, IT — 45.5416°N, 10.2118°E";
    const WEAPON:   &str = "Rust 🦀";                 // zero-cost, fearless, no GC
    const TARGETS:  &[&str] = &["Game Boy", "i8080", "Chip-8"];
    const HERESY:   &str = "Rust → wasm32 → cursed little web apps";
    const SHIELDS:  &[&str] = &["DDD", "event sourcing", "TDD", "good design"];

    fn main(&self) -> ! {
        loop { self.emulate(); self.refactor(); self.ship(); }   // -> never returns
    }
}
```

<br/>

### `.text:0000` — the main loop, disassembled

<pre>
ADDR   BYTES       LABEL    MNEMONIC              ; comment
────   ─────────   ──────   ──────────────────   ─────────────────────────
0000   F3          reset:   DI                    ; mask interrupts, find focus
0001   31 FF FF             LXI  SP,$FFFF         ; stack = top of the coffee mug
0004   CD 40 00             CALL wake_up
0007   DB 01       .loop:   IN   curiosity        ; poll the only input that matters
0009   CD 80 00             CALL emulate_cpu      ; gameboy / i8080 / chip-8
000C   CD C0 00             CALL refactor         ; design is never *done*
000F   3E 01                MVI  A,1              ; A = 1up
0011   C3 07 00             JMP  .loop            ; 0xC3 — goto, considered essential
0014   76          halt:    HLT                   ; (unreachable; we never stop)
</pre>

<br/>

### `SYMBOL TABLE` — linked at runtime

<pre>
SYMBOL                  ADDR     .section   ROM
─────────────────────   ──────   ────────   ──────────────────────────────────
<a href="https://github.com/emadb/gameboy">gameboy</a>                 $0000    .text      Game Boy (DMG) emulator — CPU·PPU·timers
<a href="https://github.com/emadb/space_invade.rs">space_invade.rs</a>         $2000    .text      i8080 + Space Invaders   ; ◄ %rip is here
<a href="https://github.com/emadb/chip-8">chip-8</a>                  $4000    .text      Chip-8 interpreter — the first boss
<a href="https://github.com/emadb/snakers">snakers</a>                 $6000    .game      Snake, in Rust
<a href="https://github.com/emadb/gol-rs">gol-rs</a>                  $7000    .game      Conway's Game of Life
<a href="https://github.com/emadb/reners">reners</a>                  $8000    .util      mass file renamer
<a href="https://github.com/emadb/lorx-display">lorx-display</a>            $E000    .device    ESP32 + e-ink — real silicon 🛸
<a href="https://github.com/emadb/meryclaire">meryclaire</a>              $F000    .elixir    static blog generator
<a href="https://github.com/emadb/ruby_loves_ddd">ruby_loves_ddd</a>          $F400    .ruby      DDD sample app
<a href="https://github.com/emadb/the_little_alchemist">the_little_alchemist</a>    $F800    .elixir    "The Little Schemer", functionally
</pre>

<br/>

### `REGISTER DUMP @ panic` — current state of the machine

<pre>
A   0x52   0101 0010    ; 'R' — accumulator pinned to Rust
B   0xBE   1011 1110    ; the BEAM, still warm
C   0xC0   1100 0000    ; Clean Code
D   0xDD   1101 1101    ; Domain-Driven Design
PC  0x1337              ; program counter -> /emulators
SP  0xFFFF              ; stack: maxed (side projects overflowing)
F   ----   S Z A P C    ; flags: [S]leep-deprived [Z]en [C]affeinated
</pre>

<br/>

<details>
<summary><b><code>thread 'main' panicked</code> — expand backtrace</b></summary>

<br/>

```text
thread 'main' panicked at 'too many side projects', src/life.rs:42:1
stack backtrace:
   0:  emadb::just_one_more_emulator
   1:  core::result::Result::<Coffee>::unwrap
   2:  emadb::refactor::{{closure}}        // "it's almost good enough"
   3:  emadb::defend_earth
   4:  <Curiosity as Iterator>::next
   5:  emadb::main::loop                   // 0x1337
note: run with `RUST_BACKTRACE=full` for a more verbose ego
note: process did not exit. it never does.
```

</details>

<br/>

<div align="center">

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=emadb&layout=compact&langs_count=8&theme=dark&hide_border=false&border_color=5FFF5F&bg_color=000000&title_color=5FFF5F&text_color=33CC33" alt="Top Languages" />

<br/>
<br/>

<pre>
// TRANSMISSION ENDS
01100111 01101111 01101111 01100100 00100000 01100011 01101111 01100100 01100101
EOF — checksum 0xDEADBEEF — &lt;invaders still descending&gt;
</pre>

<a href="https://github.com/emadb">
  <img src="https://komarev.com/ghpvc/?username=emadb&color=5FFF5F&style=for-the-badge&label=0x_HITS" alt="hits" />
</a>

</div>
