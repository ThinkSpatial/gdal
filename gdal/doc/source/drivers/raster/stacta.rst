.. _raster.stacta:

================================================================================
STACTA - Spatio-Temporal Asset Catalog Tiled Assets
================================================================================

.. versionadded:: 3.3

.. shortname:: STACTA

.. built_in_by_default::

This driver supports opening JSON files following the
`Spatio-Temporal Asset Catalog Tiled Assets <https://github.com/radiantearth/stac-spec/tree/master/extensions/tiled-assets>`_
specification. Such JSON file references tiles (also called metatiles), split
from a potentially big dataset according to a tiling scheme, with several zoom
levels. The driver provides a single raster view, with overviews, of the dataset
described by the JSON file. The driver supports metatiles of arbitrary size.

Open syntax
-----------

STACTA datasets/subdatasets can be accessed with one of the following syntaxes:

* ``filename.json``: local file

* ``STACTA:"https://example.com/filename.json"``: remote file

* ``STACTA:"filename.json":my_asset``: specify an asset of a local/remote file

* ``STACTA:"filename.json":my_asset:my_tms``: specify an asset and tiling scheme of a local/remote file

Open options
------------

The following open option is supported:

* ``WHOLE_METATILE`` = YES/NO. If set to YES, metatiles will be entirely downloaded
  (into memory). Otherwise by default, if metatiles are bigger than a threshold,
  they will be accessed in a piece-wise way.

Subdatasets
-----------

If a STACTA JSON file contains several asset templates and/or tiling scheme,
the driver will return a list of subdataset names to open each of the possible
subdatasets.

Driver capabilities
-------------------

.. supports_virtualio::
