# Practical guide through the SEP2

## Prerequisites

* Sardana server with `sar_demo` environment
* An instance of `BasicTwoDController` and its axis added to the Pool - TODO: separate `DummyTwoDController` into two: basic (only Value) and dummy (Value and ValueRef)

## Documentation

For the moment there is no written documentation (this may change after this week's Docs Camp). But we have:

* [SEP2 document](https://github.com/reszelaz/sardana/blob/sep2/doc/source/sep/SEP2.md)
* [SEP2 PR](https://github.com/sardana-org/sardana/pull/775)
* DummyTwoDController - TODO: add link
* LimaTwoDController - TODO: add link
* this guide:)

## Review scope of SEP2

* Value reference configuration (pattern & enable/disable) upstream flow
    * experimental channel level
    * measurement group level
* Value reference reporting (value vs. value reference) downstream flow
* VDS when value references point to a dataset of another HDF5 file

## Single channel acquisition

0. Configure timer for 2d channels:
   ```
   Door> twod01.timer='__self'
   Door> btwod01.timer='__self'
   ```
1. Review interface of a channel with and without referencing capability
   ```
   $> taurusform twod01 btwod01
   ```
   TODO: PoolChannelTaurusValue?
   * Demonstrate two classes definition (inheritance from `Referable` class)
2. Acquire to return value:
   ```
   Door> ct 0.1 twod01
   Door> ct 0.1 btwod01
   ```
3. Enable value reference reporting in dummy 2D and acquire:
   ```
   Door> twod01.ValueRefEnabled = True
   Door> ct 0.1 twod01
   ```
5. Configure value reference pattern in dummy 2D to return a non HDF5 URI and acquire:
   ```
   Door> twod01.ValueRefPattern = "file:///tmp/test_image.edf"
   Door> ct 0.1 twod01
   ```
6. Configure value reference pattern in dummy 2D to return a HDF5 URI and acquire:
   ```
   Door> twod01.ValueRefPattern = "h5file:///tmp/test_image.h5"
   Door> ct 0.1 twod01
   ```
   ```
   $> ls /tmp/test_*
   ```
7. Configure dummy 2D to save the HDF5 file:
   ```
   Door> twod01.SavingEnabled = True
   Door> ct 0.1 twod01
   ```
   ```
   $> ls /tmp/test_*
   ```
   
## Measurement group acquisition

TODO

## Scans

TODO

### Step scan

TODO

### Continous scan

TODO

## What else could be done and was out of SEP2 scope

* abstraction of external image processing (ROI, binning, etc)
* TODO...