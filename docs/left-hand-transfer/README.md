# Left Hand 2 policy transfer evidence

The [evidence release](https://github.com/sheilsarda2/wuji-mjlab/releases/tag/left-hand-transfer-evidence-a14da8e)
contains rollout videos and the complete experiment archive for source commit
[`a14da8e`](https://github.com/sheilsarda2/wuji-mjlab/tree/a14da8e95d95219d1325637453cfe5cd8fe9af24).
GitHub blocks new LFS uploads to public forks, so this package uses release
attachments. This branch stores the result index and file hashes.

## Final captures

Each condition is a 20-second rollout with seed 42. Both comparison panels use
the official left Hand 2.2 model. The left panel passes native left-hand
observations to the released right-hand checkpoint; the right panel mirrors
the observations. Both use the same mirrored grasp and reference setup.
The weights and corresponding joint commands stay unchanged.

| Task | Direct transfer | Adapted transfer | Video |
|---|---|---|---|
| Cube reorientation | Cube retained, 0 targets | Cube retained, 9 targets | [MP4](https://github.com/sheilsarda2/wuji-mjlab/releases/download/left-hand-transfer-evidence-a14da8e/final-cube-comparison.mp4) |
| PenSpin | Pen dropped, mean position error 45.90 cm | Pen retained, mean position error 0.58 cm | [MP4](https://github.com/sheilsarda2/wuji-mjlab/releases/download/left-hand-transfer-evidence-a14da8e/final-penspin-comparison.mp4) |

These are single-seed simulation checks using the right-hand actuator
calibration. PenSpin play disables tracking-error terminations, so zero resets
alone does not establish success. Hardware performance remains unvalidated.

## Reproduce and verify

Follow the [run instructions at the tested source revision](https://github.com/sheilsarda2/wuji-mjlab/blob/a14da8e95d95219d1325637453cfe5cd8fe9af24/docs/left_hand_playback.md).
The final captures use the published `v2026.9.27` checkpoints and the source
revision's pinned `wuji-description` submodule.

Download the [complete evidence archive](https://github.com/sheilsarda2/wuji-mjlab/releases/download/left-hand-transfer-evidence-a14da8e/left-hand-transfer-evidence.zip)
for the raw videos, NPZ trajectories, per-step JSON metrics, test logs, comparison
recipes and original beta2 experiment. Its README distinguishes the original
captures from the final clean-commit captures.

[`RELEASE-ASSETS.json`](RELEASE-ASSETS.json) records every release attachment's
size and SHA-256 digest. [`ARTIFACTS.json`](ARTIFACTS.json) covers the archive's
contents, and [`EXPERIMENT.json`](EXPERIMENT.json) indexes the trials and results.

The original beta2 comparisons are also available directly:
[cube](https://github.com/sheilsarda2/wuji-mjlab/releases/download/left-hand-transfer-evidence-a14da8e/original-cube-left-comparison.mp4)
and [PenSpin](https://github.com/sheilsarda2/wuji-mjlab/releases/download/left-hand-transfer-evidence-a14da8e/original-penspin-left-comparison.mp4).

## Compare left and right hands

The [2×2 left/right comparison](left-right-grid/README.md) places cube reorientation above PenSpin, with the adapted left hand in the left column and the original right-hand policy in the right column. It preserves the earlier direct-transfer controls above.
