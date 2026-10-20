# Quantifying Pressing in Professional Football using Tracking Data

A Master's thesis project investigating how professional football
pressing can be detected, modelled, and evaluated using high-frequency
tracking data combined with event information.

**MSc in Data Science --- University of Southern Denmark (SDU)**

## Project Overview

Pressing is a continuous and context-dependent tactical behaviour that
is difficult to represent using isolated match events or single-frame
measurements.

This project develops a **context-aware, sequence-based framework** for
detecting and evaluating settled high-pressing behaviour. The framework
combines player and ball tracking data with event data to transform raw
spatiotemporal observations into interpretable pressing sequences.

The analysis focuses specifically on **settled high pressing during
organised opposition build-up**, rather than counter-pressing or deeper
defensive phases.

## Objectives

The project aims to:

-   Detect settled high-pressing sequences using spatial, temporal, and
    contextual information.
-   Model pressing as a continuous tactical process rather than isolated
    defensive actions.
-   Evaluate pressing effectiveness using tactical outcomes and a
    composite press score.
-   Produce interpretable visual and analytical representations of
    collective defensive behaviour.

## Methodology

The analytical pipeline consists of several main stages:

1.  **Data integration** --- tracking, event, and match metadata are
    brought into a common analytical representation.
2.  **Tracking--event synchronization** --- event timestamps are aligned
    with the 25 Hz tracking data.
3.  **Context construction** --- possession, ball carrier, anticipated
    possession, attacking direction, ball state, and the pressing zone
    are inferred or constructed.
4.  **Pressing-run detection** --- defender movement intensity, movement
    direction, distance closing, and temporal persistence are combined
    to identify individual pressing runs.
5.  **Sequence modelling** --- individual pressing runs are grouped into
    continuous pressing sequences, including continuity logic across
    passing phases and brief interruptions.
6.  **Outcome evaluation** --- sequences are classified according to
    their tactical outcome and assigned a composite press score
    incorporating outcome, duration, and defender--target proximity.
7.  **Visualisation and validation** --- spatial and temporal pressing
    patterns are visualised, with selected sequences qualitatively
    inspected using match footage.

The framework therefore treats pressing as a **dynamic tactical
process** rather than a collection of independent frame-level events.

## Technologies

-   Python
-   NumPy
-   pandas
-   Matplotlib
-   XML and JSON data processing
-   Jupyter Notebook

## Results

The framework was evaluated on a professional football match and
detected:

-   **148 pressing sequences**
-   **13,939 active pressing frames**
-   Mean sequence duration of **3.15 seconds**
-   Sequence durations ranging from **0 to 23.60 seconds**
-   Press scores ranging from **0.087 to 0.977**

The analysis showed meaningful spatial and temporal variation in
pressing behaviour and demonstrated that the framework could frequently
identify coherent sequence initiation, continuation, and termination.

The outcome analysis also distinguished between different forms of
tactical impact, including clean possession regains, forced sideways
progression, and presses being bypassed.

Because the evaluation is based on a single professional match, the
results should be interpreted as an exploratory case study rather than a
universally generalisable model.

## Data Availability

The project uses professional football tracking and event data provided
through a collaboration involving the Danish Football Association (DBU).

The original tracking and event data are **not included in this
repository** because they are subject to data-sharing restrictions and
cannot be redistributed.

The repository therefore contains the thesis, presentation, and Jupyter
Notebook rather than the underlying raw dataset. The notebook preserves
the analytical workflow and rendered outputs, but it cannot be executed
from start to finish without access to the original data and the
corresponding local data paths.

## Repository Contents

  ------------------------------------------------------------------------
  File                                 Description
  ------------------------------------ -----------------------------------
  `pressing_analysis.ipynb`            Main Jupyter Notebook containing
                                       the data-processing,
                                       pressing-detection,
                                       sequence-modelling, scoring, and
                                       visualisation workflow. Rendered
                                       outputs are retained for
                                       inspection.

  `thesis_report.pdf`                  Full Master's thesis describing the
                                       research motivation, methodology,
                                       results, limitations, and
                                       conclusions.

  `thesis_defense_presentation.pptx`   Thesis defense presentation
                                       providing a concise visual overview
                                       of the project and its main
                                       findings.
  ------------------------------------------------------------------------

## Limitations and Future Work

The thesis identifies several limitations, including:

-   Ambiguity in defining the exact boundaries of continuous pressing
    sequences.
-   Sensitivity to manually selected detection and scoring parameters.
-   Dependence on the richness and granularity of the available event
    annotations.
-   Evaluation on a single professional match.

Potential future developments include adaptive sequence modelling,
richer tactical context such as passing lanes and team shape,
data-driven parameter optimisation, expert annotations, and validation
across multiple matches and teams.

## Author

**Shameek Khaled Egok**

MSc in Data Science\
University of Southern Denmark
