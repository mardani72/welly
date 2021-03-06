# CHANGES.md

## 0.4.6, winter 2019-2020

## 0.4.5, 14 November 2019
- Allowed adding the NULL value when writing an LAS file with `w.to_las()`.

## 0.4.4, 22 October 2019
- Dropped support for Python 2.7 and Python 3.4, and added support for Python 3.7 and 3.8.
- Fixed `location`, whose changes were inadvertently rolled back.

## 0.4.3, October 2019
- You can now pass an `alias` dictionary to `Well.df()`, along with the list of `keys`. You can pass `keys` and `alias` to `Project.df()` as well.
- A new function, `location.trajectory()`, generates an evenly sampled trajectory, given a sample spacing in metres.
- Added `location.plot_plan()` and `location.plot_3d()` for plotting well trajectories.
- Added a new tutorial notebook, `tutorials/Location.ipynb` to demonstrate the well path capabilities of `Well.location()`. The notebook does not cover geographic CRS's. There's still a short example in `Well.ipynb`. 
- Fixed some buggy behaviour when creating 'empty' wells, and added example to top of `tutorials/Well.ipynb`. 
- You can now pass a URL directly to `Well.from_las()` and it will try to read it.

## 0.4.2, April 2019
- Implemented basis updating when slicing. In general, you probably want to 'slice' (get a subcurve) using `curve.to_basis()` because you can use depth to get the section you want. But if you want to use indexing, like `curve[100:110]`, this operation now updates `curve.start` so that `curve.basis` is therefore updated.
- Breaking change: `utils.top_and_tail` now only works on single arrays, and returns a single array.

## 0.4.1, 24 November 2018
- Fixed a bug in `project.df()` that was building the DataFrame incorrectly.

## 0.4.0, 20 November 2018
- There are breaking changes in this release.
- Export the curves in the current `well.data` to Pandas DataFrame with `well.df()`. Previously, this function returned the DataFrame of the associated LAS file, which is still available in `well.las.df()`. 
- Export the curves in the current Project as a Pandas DataFrame with a dual index: UWI and depth.
- Made the APIs of various functions more consistent, e.g. with `keys` always being before `basis`. This regularization will continue.
- Made the way to retrieve `keys` more consistent, using the flattened list of keys, if provided, or getting all those keys corresponding to curves, if not. Some of the well methods used to break if there were striplogs in `well.data`, but they should behave a bit better now.
- Thanks to Jesper Dramsch, the documentation should now be working again. Thanks Jesper!
- Added this `CHANGES.md` file.
- Synthetics don't work anyway and are definitely broken right now. Test is withheld for now.

## 0.3.5, 20 March 2018

## 0.3.4, 15 November 2017
