<div align="center">

<pre>
███████╗███╗   ███╗ █████╗ ██████╗ ██████╗ 
██╔════╝████╗ ████║██╔══██╗██╔══██╗██╔══██╗
█████╗  ██╔████╔██║███████║██║  ██║██████╔╝
██╔══╝  ██║╚██╔╝██║██╔══██║██║  ██║██╔══██╗
███████╗██║ ╚═╝ ██║██║  ██║██████╔╝██████╔╝
╚══════╝╚═╝     ╚═╝╚═╝  ╚═╝╚═════╝ ╚═════╝ 
</pre>

`an 8-bit human · homebrew CPU · serial no. EMADB-8 · made in Brescia 🇮🇹`

<a href="https://github.com/emadb">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=900&color=8A2BE2&center=true&vCenter=true&width=620&height=46&lines=fn+main()+%7B+rebuild_the_machine()+%7D;Game+Boy.+Space+Invaders.+Chip-8.;I+don't+read+the+manual.+I+write+the+emulator.;loop+%7B+learn();+build();+ship();+%7D" alt="what I do" />
</a>

<br/>

[![Website](https://img.shields.io/badge/Website-emanueledelbono.it-8A2BE2?style=for-the-badge&logo=google-chrome&logoColor=white)](http://emanueledelbono.it)
[![Bluesky](https://img.shields.io/badge/Bluesky-@emadb-0085ff?style=for-the-badge&logo=bluesky&logoColor=white)](https://bsky.app/profile/emadb.bsky.social)
[![Blog](https://img.shields.io/badge/Blog-PlasticBlog-ff4400?style=for-the-badge&logo=rss&logoColor=white)](https://blog.codiceplastico.com)

</div>

<br/>

```console
$ ./emadb-8 --power-on
[ OK ]  cpu ......... software engineer  @ ~2 MHz of coffee
[ OK ]  role ........ co-founder @ CodicePlastico
[ OK ]  bios ........ DDD · event sourcing · actor model · TDD
[ OK ]  hobby ....... writing emulators for machines older than me
[ OK ]  location .... Brescia, Italy
[WARN]  free time ... allocation failed (too many side projects)
> READY.
```

<br/>

### 🧠 `REGISTERS` — the current state of me

<table>
<tr>
<td>

```asm
A  = Rust 🦀     ; accumulator
B  = Elixir      ; the BEAM is home
C  = Ruby        ; old friend
D  = JavaScript  ; when the web calls
```

</td>
<td>

```asm
PC -> emulators  ; program counter
SP -> low-level  ; bits, bytes, opcodes
IX -> DDD        ; index into clean design
IY -> embedded   ; ESP32 & real silicon
```

</td>
</tr>
</table>

> Currently fetching, decoding & executing curiosity about **CPU internals**, **timing accuracy**, and **how the machine really works underneath**.

<br/>

### 🗺️ `MEMORY MAP` — where my code lives

<pre>
ADDR    SEGMENT             CONTENTS
─────   ─────────────────   ────────────────────────────────────────────
$0000   [ BOOT ROM ]        <a href="https://github.com/emadb/gameboy">gameboy</a>           Game Boy (DMG) emulator — CPU · PPU · timers
$0140   [ CARTRIDGE ]       <a href="https://github.com/emadb/space_invade.rs">space_invade.rs</a>   Intel 8080 + Space Invaders, arcade-accurate
$0280   [ INTERPRETER ]     <a href="https://github.com/emadb/chip-8">chip-8</a>            Chip-8 — the hello-world of emulation
─────   ─────────────────   ────────────────────────────────────────────
$1000   [ VRAM / GAMES ]    <a href="https://github.com/emadb/snakers">snakers</a>           Snake, in Rust
$1200   [ VRAM / GAMES ]    <a href="https://github.com/emadb/gol-rs">gol-rs</a>            Conway's Game of Life
─────   ─────────────────   ────────────────────────────────────────────
$2000   [ I/O PORTS ]       <a href="https://github.com/emadb/reners">reners</a>            massive file renamer
$3000   [ HARDWARE ]        <a href="https://github.com/emadb/lorx-display">lorx-display</a>      ESP32 + e-ink thermostat — actual silicon!
─────   ─────────────────   ────────────────────────────────────────────
$F000   [ HIGH MEM ]        <a href="https://github.com/emadb/meryclaire">meryclaire</a>        static blog generator (Elixir)
$F400   [ HIGH MEM ]        <a href="https://github.com/emadb/ruby_loves_ddd">ruby_loves_ddd</a>    Domain-Driven Design sample (Ruby)
$F800   [ HIGH MEM ]        <a href="https://github.com/emadb/the_little_alchemist">the_little_alchemist</a>  "The Little Schemer", functionally
</pre>

<br/>

### 🧾 `INSTRUCTION SET` — what I run on

| MNEMONIC | OPCODE | CYCLES | DESCRIPTION |
|:---------|:------:|:------:|:------------|
| `RUST`   | `$52`  |  `∞`   | systems programming, zero-cost abstractions, no GC |
| `EMU`    | `$E0`  | `hi`   | cpu emulation — opcode decode, cycle timing, memory maps |
| `DDD`    | `$DD`  |  `8`   | domain-driven design, bounded contexts, ubiquitous language |
| `EVS`    | `$E5`  |  `6`   | event sourcing & the actor model |
| `TDD`    | `$7D`  |  `4`   | red · green · refactor — every cycle |
| `TALK`   | `$7A`  |  `?`   | conferences: WebDay · Codemotion · RubyDay |

<br/>

<details>
<summary><b>🛠️ <code>CORE DUMP</code> — expand for raw memory</b></summary>

<br/>

```ruby
emadb = Human.new do |dev|
  dev.believes   "the best way to understand X is to rebuild X"
  dev.fascinated_by ["opcodes", "timing diagrams", "bit manipulation"]
  dev.day_job    "crafting robust software @ CodicePlastico"
  dev.night_job  "convincing dead CPUs to run again"
  dev.ask_me_about ["emulation", "DDD", "event sourcing", "functional programming"]
  dev.fun_fact   "I write emulators for hardware I never owned as a kid"
end

emadb.coffee.refill while emadb.awake?
```

</details>

<br/>

<div align="center">

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=emadb&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&bg_color=00000000&title_color=8A2BE2&text_color=c9d1d9" alt="Top Languages" />

<br/>
<br/>

<code>HALT.</code> &nbsp;·&nbsp; thanks for executing this program.

<br/>
<br/>

<a href="https://github.com/emadb">
  <img src="https://komarev.com/ghpvc/?username=emadb&color=8A2BE2&style=for-the-badge&label=CYCLES+RUN" alt="Profile Views" />
</a>

</div>
