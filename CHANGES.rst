===============
 Release notes
===============

DISCOVER packages are made available for both Python and R. The
packages for both languages expose the same set of features and a
similar programming interface, where differences in the latter only
serve to conform to language-specific conventions. Increments of the
major or minor version number (e.g. 0.9 -> 1.0, or 1.0 -> 1.1) will be
made upon the introduction of substantial new features. Bug fixes or
smaller new features are introduced in the patch releases
(e.g. 0.9.1). Whereas the major and minor release series will always
be kept in sync between Python and R, patch releases may be published
independently. In other words, version 0.9.3 of the Python package
would not have more functionality than version 0.9.1 of the R package;
it would simply have required more bug fixes. However, version 1.0.0
of the Python package would have features that do not exist in version
0.9.1 of the R package.


0.9 series
==========

:Latest Python version:  0.9.4 (July 28, 2021)
:Latest R version:       0.9.4 (July 28, 2021)


Python package
--------------

0.9.4 (July 28, 2021)
~~~~~~~~~~~~~~~~~~~~~

**Added**:

- The new fdr_method argument of the pairwise_discover_test function
  selects the false discovery rate estimation method used for multiple
  testing correction. Its default value selects a Benjamini-Hochberg
  procedure adapted for discrete test statistics. As an alternative,
  the standard Benjamini-Hochberg procedure can be selected. While the
  latter is much faster, it is also more conservative than the
  discrete version. The discrete method was always used in previous
  versions and is still the recommended choice.

**Changed**:

- Speed improvements in DiscoverMatrix and
  pairwise_discover_test. DiscoverMatrix finishes instantaneously for
  small to medium-sized data sets and takes only a few seconds for
  very large data sets. pairwise_discover_test (with discrete
  Benjamini-Hochberg) is about twice as fast as in previous versions.

- Python 2.7 is no longer supported.

**Fixed**:

- If pandas >= 1.0 was installed, subsetting a DiscoverMatrix object
  gave rise to "AttributeError: 'DataFrame' objects has no attribute
  'ix'".

- Fixed the underlying Fortran code to make it compile with GNU
  Fortran >= 10. Due to these changes the minimum supported GNU
  Fortran version is now version 5.


0.9.3 (June 18, 2019)
~~~~~~~~~~~~~~~~~~~~~

**Fixed:**

- Applied a small fix to the Fortran code to make it compile with GNU Fortran >= 8.2.


0.9.2 (April 20, 2018)
~~~~~~~~~~~~~~~~~~~~~~

**Added:**

- Added a new conda recipe, which takes advantage of features introduced by conda build 3.

**Fixed:**

- The RuntimeWarning fix added in version 0.9.1 did not work when the
  pairwise_discover_test function was given a grouping factor.


0.9.1 (October 11, 2017)
~~~~~~~~~~~~~~~~~~~~~~~~

**Fixed:**

- Removed the "RuntimeWarning: invalid value encountered in less"
  warnings generated by the PairwiseDiscoverResult class' __repr__ and
  significant_pairs methods


0.9 (September 23, 2016)
~~~~~~~~~~~~~~~~~~~~~~~~

First public release


R package
---------

0.9.4 (July 28, 2021)
~~~~~~~~~~~~~~~~~~~~~

**Added**:

- The new fdr.method argument of the pairwise.discover.test function
  selects the false discovery rate estimation method used for multiple
  testing correction. Its default value selects a Benjamini-Hochberg
  procedure adapted for discrete test statistics. As an alternative,
  the standard Benjamini-Hochberg procedure can be selected. While the
  latter is much faster, it is also more conservative than the
  discrete version. The discrete method was always used in previous
  versions and is still the recommended choice.

**Changed**:

- Speed improvements in discover.matrix and
  pairwise.discover.test. discover.matrix finishes instantaneously for
  small to medium-sized data sets and takes only a few seconds for
  very large data sets. pairwise.discover.test (with discrete
  Benjamini-Hochberg) is about twice as fast as in previous versions.

- The matrixStats package is no longer a dependency.

**Fixed**:

- Re-enabled OpenMP, which distributes the computations in
  pairwise.discover.test across multiple CPUs. OpenMP was disabled
  since R 4.0.

- Fixed the underlying Fortran code to make it compile with GNU
  Fortran >= 10. Due to these changes the minimum supported GNU
  Fortran version is now version 5.


0.9.3 (June 18, 2019)
~~~~~~~~~~~~~~~~~~~~~

**Fixed:**

- Applied a small fix to the Fortran code to make it compile with GNU Fortran >= 8.2.


0.9.2 (October 11, 2017)
~~~~~~~~~~~~~~~~~~~~~~~~

**Added:**

- Added citation info to the R package, use with
  `citation("discover")`

**Fixed:**

- Fixed a bug in pairwise.discover.out's print method that caused the
  value of the fdr.threshold argument to be ignored


0.9.1 (September 23, 2016)
~~~~~~~~~~~~~~~~~~~~~~~~~~

First public release
