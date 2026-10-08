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
