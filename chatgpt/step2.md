## Step 2: Proposed sample set

I recommend this eight-sample set for **Night Shift**. It covers the drum foundation, bass, mechanical texture, and metallic accents, with **29,300 bytes** of raw sample data total. Volumes are provisional starting values in hex; final balance and suitability depend on your MilkyTracker audition.

| ID | Sample | Role | Raw size / peak | Recorded envelope | Start volume | Finetune | Note range | Loop |
|---|---|---|---:|---|---:|---:|---|---|
| 01 | ST-01 `BassDrum3` | Main kick | 3,400 B / 128 | Strong attack, steady decay to a quiet tail | 2A | 00* | C-4–B-5 | None |
| 02 | ST-01 `Snare4` | Snare hit | 2,000 B / 128 | Sharp attack, steep decay | 24 | 00* | C-3–B-4 | None |
| 03 | ST-01 `HiHat1` | Noisy hat | 1,400 B / 127 | Irregular, bright texture with a noticeable tail | 12 | 00* | C-3–B-4 | None |
| 04 | ST-01 `DigDug` | Bass line | 3,100 B / 108 | Dips after the attack, then grows more stable toward the end | 28 | 00* | C-4–B-5 | Forward-loop trial |
| 05 | ST-01 `Mechanic1` | Rising mechanical accent | 7,500 B / 124 | Builds in level across the sample | 18 | 00* | C-3–B-4 | None |
| 06 | ST-01 `MetalKeys` | Metallic pitched motif | 9,400 B / 127 | Sustained body with a fairly even level | 18 | 00* | C-3–B-4 | Forward-loop trial |
| 07 | ST-01 `SynClaves` | Industrial tick or clank | 1,000 B / 127 | Very sharp attack and fast decay | 1C | 00* | C-3–B-4 | None |
| 08 | ST-02 `Cowbell2` | Metallic accent | 1,500 B / 128 | Strong attack and rapid decay | 18 | 00* | C-3–B-4 | None |

\* I couldn’t verify historical finetune values for these samples. Use **00** as the initial audition setting, not as a confirmed historical value. The online ST-01 research I found identifies `Mechanic1` as a D-50 Intruder FX sound, `MetalKeys` as a DX21 Metal Keys preset, and `SynClaves` as a DX21 Breakin preset; it doesn’t give tracker finetune settings. 

No loops are committed yet. `DigDug` and `MetalKeys` are the two candidates I’d audition for forward loops; choose exact points only if the loop sounds smooth in MilkyTracker.

The archive samples were analyzed as signed 8-bit raw data. The peak and envelope readings inform these starting volumes, but they don’t establish audible loudness or musical suitability. Please audition each sample for tone, useful pitch range, level against the others, and how it sits in the four-channel mix. For the two loop candidates, check for clicks, pitch jumps, or an unnatural repeated texture.

At **29.3 KB** of raw samples, the set leaves room for roughly nine 1 KB pattern blocks within the bootstrap’s 40 KB bonus target, before any format-specific overhead. Static sample analysis is complete; finetunes, final volumes, loops, and sample acceptance remain pending your audition.

---

Yes, you won't find finetune values for these samples because they predate finetune. Apologies if my new_bootstrap file said otherwise.

---

Understood. The bootstrap’s instruction to look up historical finetunes was mistaken. I’ll use **00** as the starting setting and make any finetune changes only if your audition calls for them.