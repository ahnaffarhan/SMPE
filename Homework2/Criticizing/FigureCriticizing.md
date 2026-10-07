# Scientific Methodology and Performance Evaluation: Graphics Critique Report

This report evaluates and redesigns four flawed graphics from Jean-Marc's slides using the established checklist for good graphics[cite: 1, 2]. Each figure is critiqued for its classical errors and redesigned using `ggplot2` in R to ensure compliance with data visualization principles.

## Figure 1: Banana Exports (1994-2005)

### Critique
* **Confusing Scales & Non-Necessary Information:** The 3D perspective creates confusing scales, making it difficult to accurately read the values. The banana background image introduces non necessary informations and violates the principle to minimize ink.
* **Occam's Razor:** If two representations contain the same information, choose the simpler one. A 3D chart is unnecessarily complex for this data.
* **Categorical Ordering:** The countries on the x-axis are not based on classical ordering (e.g., alphabetical or from best to worst). 

### Better Representation
A 2D faceted line chart eliminates the 3D distortion, removes the background image, and handles multiple countries without overcrowding a single graph (which keeps the number of curves on a same graph small). 

![Figure 1: Banana Exports](Rplot.png)

