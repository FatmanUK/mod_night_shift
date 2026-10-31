# Unnamed Mod: **Initial** Project Bootstrap File

Gah! I've used an old new_bootstrap format! :( 

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

The `.mod` should be 180+-15 seconds long, but exact final runtime is not important. Musical flow, authenticity, and ProTracker compatibility matter more.

Since we're insisting on PT2 compatibility, there are to be no XM-only features.

---

## First Steps

### 1. Select a title for this masterpiece

Suggest ten possible titles which reflect the intended character as specified above. A title isn't strictly necessary, but having one helps keep the musical direction consistent. It gives the piece a little identity before pattern00 is even composed. The suggested titles should be short, evocative, and technical without being overly descriptive. The user will pick the best one.

Assign an appropriate speed and beats-per-minute.

### 2. Select a solid sample set

Select eight samples from the ST-01 and ST-02 archives which will accomplish the goal and achieve the desired character for the `.mod`. State which samples are to be looped, if any. The user will determine exact loop points and accept or reject samples for looping. Forward loops are the only kind of loops allowed per **ProTracker 2** compatibility rules.

Analyse the samples' envelopes and recommend default volume settings for each one. Note recorded peak and envelope behaviour. If you don't have access to the samples, report this lack and the user will upload the samples.

Finetune will also be determined at this point. Since we're using only ST-01 and ST-02 samples, historical finetune values **should be** available on the web. Find and report them for audition by the user. If a historical finetune value isn't found for a sample, make a note for the user to determine the finetune value. The user will report any adjusted finetune values.

Generate note-range maps. Per **PT2** compatibility rules, only octaves 3-5 are allowed. Low-pitched samples should be restricted to octaves 4-5, and high-pitched samples should be restricted to octaves 3-4.

Suggest audition criteria for the samples. The user will audition the sample set based on these criteria.

### 3. Write a structural arc and a motif map

The structural arc should be a narrative guiding the creation of patterns and their reuse in the order list. The structural arc springs forth from the name of the piece, which is our narrative and thematic 'seed'.

Each motif has a descriptive character. For example:

- Motif A: heartbeat kick + bass pulse
- Motif B: descending pad figure
- Motif C: metallic chime
- Motif D: chromatic tension figure

Then each pattern becomes a recombination of those motifs. Do not use this exact example in your motif map.

When this step is complete, remind the user that now is a good time to generate an updated bootstrap markdown file.

---

## Compatibility Rules

```text
4 channels only
ProTracker-compatible effects only
No XM-only composition features
No notes below C-3
No notes above B-5
Forward sample loops only
No ping-pong loops
Pattern reuse preferred
Exact final runtime is unimportant
```

Bonus points if the final `.mod` weighs in at less than 40KB.

## Arbitrary Guidelines

- Unless otherwise specified or required, output lone numbers in hex format (eg. "3f").
- Explain effects the first time they're used.

## Tools Used

Testing Operating System: PikaOS
Testing Tracker: MilkyTracker

The patterns will not be entered into MilkyTracker directly. Instead, I have written a compiler for the final `.mod`. The compiler requires pattern rows in a specific format, as follows:

`| RR | NNN II EEE | NNN II EEE | NNN II EEE | NNN II EEE |`
where RR is the row number, NNN is the note, II is the instrument slot and EEE is the effect. The row format is compatible with MarkDown tables, so each pattern should have a MarkDown table header.
