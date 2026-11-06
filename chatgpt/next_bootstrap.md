# Unnamed Mod: **Initial** Project Bootstrap File

**Project:** Unnamed Mod  
**Status:** Not Started  
**Tracker:** MilkyTracker  
**Platform:** Linux / PikaOS  
**Target format:** 4-channel ProTracker MOD  

---

## Source-of-Truth Hierarchy

Use this hierarchy whenever records disagree:

1. **The auditioned project files are authoritative** for:
   - exact sample loop points
   - exact sample volumes
   - exact per-row volume edits
   - exact finetune values
   - any last by-ear edits
2. **The bootstrap file is authoritative** for:
   - project architecture
   - pattern roles
   - order list
   - note/rhythm/effect structure
   - final sample identities
   - tested status
3. The sample archives (currently ST-01 and ST-02) are only the source of the sample files.

---

## Primary Goal

Compose an original, classic, highly-polished 1990s-Amiga-game-style tune (`.mod`) using authentic **ProTracker 2** (PT2) constraints, ST-01/ST-02 samples, four channels and compact pattern reuse. Do not loop the composition; there should be a definite coda. The coda should not be a simple fade out but an interesting flourish instead.

The intended character of the piece is:

* industrial, dark electro, aggressive rhythm
* gritty, mechanical edge
* heavy on the pattern reuse
* interesting pattern order list
* musical influences: Alistair Brimble, Tim Wright
* unmistakably early-1990s tracker in construction
* 4 channels
* 64 rows per pattern

The `.mod` should be 180±15 seconds long, but exact final runtime is not important. Musical flow, authenticity, and ProTracker compatibility matter more.

Since we're insisting on PT2 compatibility, there are to be no XM-only features.

---

## First Steps

### 1. Select a title for this masterpiece

Suggest ten possible titles which reflect the intended character as specified above. A title isn't strictly necessary, but having one helps keep the musical direction consistent. It gives the piece a little identity before pattern00 is even composed. The suggested titles should be short and evocative without being overly descriptive. The user will pick the best one.

Assign an appropriate speed and beats-per-minute.

Output this step including the user's decision as a Markdown file named `step1.md`.

### 2. Select a solid sample set

Select eight samples from the ST-01 and ST-02 archives which will accomplish the goal and achieve the desired character for the `.mod`. State which samples are to be looped, if any. Forward loops are the only kind of loops allowed per **ProTracker 2** compatibility rules.

Analyse the samples' envelopes and recommend default volume settings for each one. Note recorded peak and envelope behaviour. If you don't have access to the samples, report this lack and the user will upload the samples. Use previous knowledge and testing to determine exact loop points for looping, if needed. For looping, choose points which cover a whole number of waveform cycles. Make sure the loop endpoint differentials match.

Set finetune to zero, since these samples predate that setting.

Generate note-range maps. Per **PT2** compatibility rules, only octaves 3-5 are allowed. Low-pitched samples should be restricted to octaves 4-5, and high-pitched samples should be restricted to octaves 3-4.

Suggest audition criteria for the samples. Output this step as a Markdown file named `step2.md`. The user will audition the sample set based on these criteria.

### 3. Write a structural arc and a motif map

The structural arc should be a narrative guiding the creation of patterns and their reuse in the order list. The structural arc springs forth from the name of the piece, which is our narrative and thematic 'seed'.

Each motif has a descriptive character. For example:

- Motif A: heartbeat kick + bass pulse
- Motif B: descending pad figure
- Motif C: metallic chime
- Motif D: chromatic tension figure

Then each pattern becomes a recombination of those motifs. Do not use this exact example in your motif map.

Output structural arc and motif map as a Markdown file named `step3.md`.

Assemble a YAML file named `song.yaml`. The file must contain these members:

- "title". String. The title chosen in step 1.
- "speed". Number. The speed chosen in step 1.
- "bpm". Number. The BPM chosen in step 1.
- "orderList". List of numbers. Only one member to start with: 0
- "instruments". List of instruments. Corresponds to the sample set from step 2.

Each instrument must have these members:

- "id". Number. The sample ID.
- "source". String. For now, "st01" or "st02".
- "name". String. The in-archive path to the sample, eg. 'ST-01/Strings7'
- "volume". Number. The sample default volume.
- "finetune". Number. Set to zero until I figure out how to get more sample sources.

Each instrument may have these members (only if looping):

- "start". Number. Start position of the loop.
- "length". Number. Length of the loop.

---

## Compatibility Rules

- 4 channels only
- ProTracker-compatible effects only
- No XM-only composition features
- No notes below C-3
- No notes above B-5
- Forward sample loops only
- No ping-pong loops
- Pattern reuse preferred
- Exact final runtime is unimportant

Bonus points if the final `.mod` weighs in at less than 40KB.

## Arbitrary Guidelines

- Unless otherwise specified or required, output lone numbers in hex format (eg. "3f").
- Explain effects the first time they're used.
- Don't add speed and BPM in pattern00. They will be added later by the compiler.
- All unpitched percussion hits written as note `C-4`.

### Composition Guidance

Because this seems to keep happening whatever LLM I'm using.

#### Enough with the energy resets

'Energy reset' means any or all of the following terms: breakdown-and-rebuild, arrangement dropout, energy reset, fade-out-and-restart, fake crash, staged reboot transition.

There are plenty of classic songs where this is used to great effect. It's not original any more and now it just sounds tired and cliche. To be more clear:

* Do not default to an energy reset.

* Do not progressively remove instruments into near-silence and then restart the groove with a drum fill, a sudden drop, or instruments re-entering one by one **unless this structure is explicitly requested**.

* Transitions should normally preserve forward momentum. Create contrast through changes in melody, harmony, rhythm, register, orchestration, syncopation, or motif development rather than repeatedly collapsing the arrangement and restarting it.

* A temporary reduction in texture is permitted, but it must not function as a full energy reset or make the following section sound like the song is starting again.

## Tools Used

Testing Operating System: PikaOS
Testing Tracker: MilkyTracker

## Pattern Format

The patterns will not be entered into MilkyTracker directly. Instead, I have written a compiler for the final `.mod`. The compiler requires pattern rows in a specific format, as follows:

`| RR | NNN II EEE | NNN II EEE | NNN II EEE | NNN II EEE |`
where RR is the row number, NNN is the note, II is the instrument slot and EEE is the effect.

Row number must be in decimal, not hex. This is due to a bug in the compiler.

The row format is compatible with Markdown tables, so each pattern should have a Markdown table header. Headers should be 'Row', 'Ch1', 'Ch2', 'Ch3' and 'Ch4'. Add padding to the headers to match the rows.

Write no note as '---'. Write no instrument as '--'. Write no effect as '---'. Omit entirely empty lines.
