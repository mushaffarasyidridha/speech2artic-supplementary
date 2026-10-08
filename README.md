# Supplementary material — From Speech to Articulator Movement

Videos of articulator movement predicted from speech, for the ten test speakers of the paper.
No test speaker was seen during training.

## Videos (`videos/`)

One video per test speaker, real time (20.8 frames/s), with the speech that drives the models.
Every frame shows three panels on the real-time MRI image:

| panel | lines |
|---|---|
| REAL vs NEW | white: contour from the MRI · green: speech → 19 vocal-tract distances → solver (proposed) |
| REAL vs OLD | white: contour from the MRI · orange: earlier speech → contour model |
| NEW vs OLD | green vs orange |

Both models are given the speaker's mean vocal-tract shape: the solver starts from the mean contour of
the recording, and the earlier model's contour is shifted so that its mean equals the real mean. The
videos therefore compare **movement**, as the paper does.

## Model output before and after the solver (`videos/solver_check/`)

The speech model outputs the 19 distances, not a contour; the solver turns them into a contour. One
video per test speaker shows whether the solver changes the prediction:

| panel | lines |
|---|---|
| left | MRI image · white: real contour · green: solver contour |
| right | 4 of the 19 distances, 6 s scrolling window: white real · blue model output · green dashed solver output, measured on its contour |

Each plot title gives the velocity correlation for every pair (model–real, solver–real, solver–model).
Over the 40 test recordings, the solved distances follow the model output at velocity r = 0.97, and
the velocity correlation with the real movement drops only from 0.53 (model output) to 0.51 (after
the solver). The solver follows the upper tongue root and the velum tip least closely (r ≈ 0.8).

## The 19 distances

Numbered as in Fig. 1 of the paper.

| # | distance |
|---|---|
| 1–3 | tongue to front, middle and back hard palate |
| 4–5 | tongue to velum middle and velum tip |
| 6 | tongue to the mouth point MM (most frequent position of the upper lip's lowest point) |
| 7–8 | upper and lower tongue root to the pharyngeal wall |
| 9 | epiglottis tip to the pharyngeal wall |
| 10 | arytenoid region to epiglottis (aryepiglottic aperture) |
| 11 | velum height |
| 12 | velopharyngeal port (horizontal, at the height of the hard palate's lowest point) |
| 13 | lip aperture |
| 14–15 | upper and lower lip height relative to MM |
| 16–17 | upper and lower lip protrusion |
| 18–19 | jaw height and protrusion |

## Data

MRI video and audio: English-75Speaker real-time MRI corpus (Lim et al., *Scientific Data* 8, 187,
2021), used under its licence. Contours: produced by the contour extractor described in Sec. 2.1 of
the paper.
