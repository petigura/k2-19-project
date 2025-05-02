# Paige, the original issue was that pip could not properly install
  numpy<2.0. I fixed this by using conda to explicitly install Kento's
  dependences, before installing our own.

# First install kento's depedences
$ conda create -n k2-19 jax conda-forge::numpyro pandas "numpy<2.0" matplotlib importlib_resources 

# Then install our dependences
pip install jnkepler

conda install conda-forge::corner seaborn dill

# I got the following qt error.

qt.qpa.plugin: From 6.5.0, xcb-cursor0 or libxcb-cursor0 is needed to load the Qt xcb platform plugin.
qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.

Available platform plugins are: eglfs, linuxfb, minimal, minimalegl, offscreen, vnc, xcb.

Aborted (core dumped)

# This is a problem with the plotting backend, so I editted the file 

/scr/paige/.config/matplotlib/matplotlibrc

```
# Use the TkAgg backend for interactive plots
backend: TkAgg

# Optional: Make plots look nicer
figure.figsize: 6, 4
axes.grid: True
font.size: 12
savefig.dpi: 150
```

to force matplotlib to use TkAgg 





