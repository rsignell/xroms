# What's New

## Unreleased

* updating versioning approach
* the xgcm grid is no longer attached to every variable in a Dataset. Because of this:
  * Several `xroms` accessor functions now require the grid to be input
  * Additionally because of the grid not being available, the Dataset is no longer available within the DataArray accessor, making it so that functions that change the grid size in any dimension no longer know about other coordinates to use. Therefore, these `xroms` accessor functions for DataArrays no longer work (e.g. ddeta, ddxi, etc). All `xroms` Dataset accessor functions still work, and the grid object is still saved to the Dataset `xroms` accessor.
* You can set up the grid object directly in your `xroms` Dataset accessor with `ds.xroms.set_grid(grid)`, otherwise it will be calculated internally.
* `xroms` functions for opening model output files will be deprecated in the future; use `xarray` functions directly instead of opening model output through `xroms`, and then run `xroms.roms_dataset()` to add functionality to your Dataset and to calculate your `xgcm` grid object.
* tests have been updated
* `xroms` works with newest version of `xgcm`
* changed all references to the `xgcm` grid to `xgrid` since there is now a "grid" attribute in some Datasets.
* updated example notebooks to be formal docs
* added a ROMS example dataset.