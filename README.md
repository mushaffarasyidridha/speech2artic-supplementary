# Supplementary material — From Speech to Articulator Movement

Videos of articulator movement predicted from speech, for the ten test speakers of the paper.
No test speaker was seen during training.

## Videos (`videos/`)

One video per test speaker (`videos/<speaker>.mp4`), real time (20.8 frames/s), with the speech that
drives the models. No test speaker was seen during training.

**Top: three MRI panels, every pair of contours**

| panel | lines |
|---|---|
| REAL vs NEW | white: contour from the MRI · green: proposed, speech → 19 vocal-tract distances → solver |
| REAL vs OLD | white · orange: earlier speech → contour model |
| NEW vs OLD | green vs orange |

**Bottom: four of the 19 distances over time** (6 s scrolling window, yellow line = current frame):
lip aperture, tongue to mid hard palate, velopharyngeal port, upper tongue root to pharyngeal wall.

| line | meaning |
|---|---|
| white | real distance, measured on the MRI contour |
| blue (thick) | NEW model output: the 19 distances themselves, before any solver |
| green dashed | NEW after the solver, measured again on the solved contour |
| orange | OLD model, measured on its contour |

Each plot title gives the velocity correlation for new–real, old–real and solver–new; the header
gives the same, averaged over all 19 distances. The solver follows the model output closely (velocity
r = 0.97 over the 40 test recordings; the velocity correlation with the real movement goes from 0.53
before to 0.51 after the solver), so the green contour shows what the model predicted.

All models are given the speaker's mean vocal-tract shape: the model output gets the recording's mean
distances, the solver starts from the mean contour, and the earlier model's contour is shifted so that
its mean equals the real mean. The videos therefore compare **movement**, as the paper does.

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
