# Berkeley BLISS Fork: Issue Tracking and Development Notes


- **Original Repository:** [n-west/bliss](https://github.com/n-west/bliss)
- **SRT BLISS Testing:** [gbezze/BLISS-for-SRT](https://github.com/gbezze/BLISS-for-SRT/blob/master/bliss_guide_SRT.md)

---

## Current Issues (from Git)

- Search runs twice when `bliss_find_hits` outputs a `.dat` file.
- `process_dedrift` integration and hit search should occur on a per-drift-block basis.
- `bland` copy operator requires more sophisticated handling of strides/slices.
- `bland` sum along axis (`statistical_launch_wrapper`) produces swapped results.
- Add option to statically link **HDF5** and **bitshuffle**.
- Update **libfmt** to a tagged release with complex number support.
- Improve **MAD SNR** estimation.
- (De)serialize **RFI** information for hits.
- Add logging functionality.

---

## Other Issues / Bugs

- `.dat` output uses incorrect whitespace, causing `find_events` to fail.
- Multiple active branches exist for overlapping issues; these should be reconciled.
- Code and development conventions are currently **GB-centric**.
- Excessive false positives at the ends of drift ranges, especially when bandpass power changes sharply (e.g., near edge nodes).
- **Desmearing algorithm:**
  - Overcompensates for lost power when signals are both wide and high-drift.
  - Uses integer multiples of unit drift rate for power recovery estimation, producing “ringing.”  
    *→ Consider supporting non-integer drift rates.*

---

## Feature Requests

- Support for alternative resolutions (e.g., “mid-res”).
- Pre-filtering of known RFI zones to reduce false positives.
- Extend search range to **50 Hz/s** drift rates.
- Achieve runtime performance suitable for **real-time pipelines**.
- Integrate directly into real-time pipelines.

---