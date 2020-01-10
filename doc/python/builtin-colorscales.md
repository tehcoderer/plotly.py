---
jupyter:
  jupytext:
    notebook_metadata_filter: all
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.3.1
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.6.8
  plotly:
    description: A reference for the built-in named continuous (sequential, diverging
      and cylclical) colorscales in Plotly.
    display_as: file_settings
    has_thumbnail: true
    ipynb: ~notebook_demo/187
    language: python
    layout: base
    name: Built-in Continuous Colorscales
    order: 27
    permalink: python/builtin-colorscales/
    thumbnail: thumbnail/heatmap_colorscale.jpg
    v4upgrade: true
---

### Using Built-In Colorscales

Many Plotly Express functions accept a `color_continuous_scale` argument and many trace
types have a `colorscale` attribute in their schema. Plotly comes with a large number of
built-in continuous colorscales, which can be referred to in Python code when setting the above arguments,
either by name in a case-insensitive string e.g. `px.scatter(continuous_color_scale="Viridis"`) or by reference e.g.
`go.Scatter(marker_colorscale=plotly.colors.sequential.Viridis)`. They can also be reversed by adding `_r` at the end
e.g. `"Viridis_r"` or `plotly.colors.sequential.Viridis_r`.

The `plotly.colours` module is also available under `plotly.express.colors` so you can refer to it as `px.colors`.

When using continuous colorscales, you will often want to [configure various aspects of its range and colorbar](/python/colorscales/).

### Named Built-In Colorscales

You can use any of the following names as string values to set `continuous_color_scale` or `colorscale` arguments.
These strings are case-insensitive and you can append `_r` to them to reverse the order of the scale.

```python
import plotly.express as px
from textwrap import wrap

named_colorscales = px.colors.named_colorscales()
print("\n".join(wrap("".join('{:<12}'.format(c) for c in named_colorscales), 96)))
```

### Built-In Sequential Colorscales

A collection of predefined sequential colorscales is provided in the `plotly.colors.sequential` module. Sequential color scales are appropriate for most continuous data, but in some cases it can be helpful to use a diverging or cyclical color scale (see below).

Here are all the built-in scales in the `plotly.colors.sequential` module:

```python
import plotly.express as px

fig = px.colors.sequential.swatches()
fig.show()
```

Note: `RdBu` was included in this module by mistake, even though it is a diverging color scale.
It is intentionally left in for backwards-compatibility reasons.

### Built-In Diverging Colorscales

A collection of predefined diverging colorscales is provided in the `plotly.colors.diverging` module.
Diverging color scales are appropriate for continuous data that has a natural midpoint
other otherwise informative special value, such as 0 altitude, or the boiling point
of a liquid. These scales are intended to be used when [explicitly setting the midpoint of the scale](/python/colorscales/#setting-the-midpoint-of-a-diverging-colorscale).

Here are all the built-in scales in the `plotly.colors.diverging` module:

```python
import plotly.express as px

fig = px.colors.diverging.swatches()
fig.show()
```

### Built-In Cyclical Colorscales

A collection of predefined cyclical colorscales is provided in the `plotly.colors.cyclical` module.
Cyclical color scales are appropriate for continuous data that has a natural cyclical
structure, such as temporal data (hour of day, day of week, day of year, seasons) or
complex numbers or other phase or angular data.

Here are all the built-in scales in the `plotly.colors.cyclical` module:

```python
import plotly.express as px

fig = px.colors.cyclical.swatches()
fig.show()
```