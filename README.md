# ![Alt text](figures/logo.png)

Read5 is a python wrapper to read fast5, slow5/blow5 and pod5 files using the same overloaded functions from different APIs.

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-teal.svg)](https://www.gnu.org/licenses/gpl-3.0)
![Python3](https://img.shields.io/badge/Language-Python_3-darkred.svg)

[![PyPI version](https://badge.fury.io/py/read5.svg)](https://badge.fury.io/py/read5)

<!-- ![conda](https://img.shields.io/badge/Uses-conda-green.svg) [![Anaconda-Server Badge](https://anaconda.org/jannessp/read5/badges/version.svg)](https://anaconda.org/jannessp/read5) ![Conda](https://img.shields.io/conda/dn/jannessp/read5) [![Conda package](https://anaconda.org/jannessp/read5/badges/latest_release_date.svg)](https://anaconda.org/jannessp/read5) [![Conda package](https://anaconda.org/jannessp/read5/badges/platforms.svg)](https://anaconda.org/jannessp/read5) -->
 
[![DOI](https://zenodo.org/badge/633012569.svg)](https://zenodo.org/badge/latestdoi/633012569)

[![Twitter Follow](https://img.shields.io/twitter/follow/Ja_Spangenberg)](https://twitter.com/Ja_Spangenberg)
___
## Table of Content
1.  [Installation](#installation)
2.  [Usage](#usage)
3.  [Full Documentation](https://jannessp.github.io/read5.github.io/)
___
## Installation

Pod5 is not available via conda (27.06.2023).
Read5 Currently available via pipy.

```bash
pip install read5
```
___
## Usage

[Click here to see a full documentation about the classes and function.](https://jannessp.github.io/read5.github.io/)

*my_file* can be a fast5, slow5, blow5 or pod5 file. The wrapper detects the file format depending on the file extension.

Small example:

```python
from read5 import read # or from read5.Reader import read

r5 = read(my_file) # file with on of these extensions: .fast5, .slow5, .blow5, .pod5
for readid in r5:
    signal = r5.getSignal(readid)
    norm_signal = r5.getZNormSignal(readid) # returns normalised read signal: norm_signal = (signal - median(signal)) / mad(signal)
    channel = r5.getChannelNumber(readid)
    sampleid = r5.getSampleID(readid)
    runid = r5.getSampleID(readid)

readid_list = r5.getReads()
```

If you want to use the file readers you can import the corresponding class like this:

```python
from read5.Fast5Reader import Fast5Reader # contains the Fast5 Reader class
from read5.Slow5Reader import Slow5Reader # contains the Slow5 Reader class
from read5.Pod5Reader import Pod5Reader # contains the Pod5 Reader class
```

## Full Documentation
Created with [pdoc3](https://pdoc3.github.io/pdoc/).
Can be found [here](https://jannessp.github.io/read5.github.io/).
