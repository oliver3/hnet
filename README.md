# HNET - Graphical Hypergeometric Networks
[![PyPI Version](https://img.shields.io/pypi/v/hnet)](https://pypi.org/project/hnet/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/erdoganta/hnet/blob/master/LICENSE)

This package detects associations in datasets across features with unknown function.

**Background** Real-world data sets often contain measurements with both continues and categorical values for the same sample. Despite the availability of many libraries, data sets with mixed data types require intensive pre-processing steps, and it remains a challenge to describe the relationships of one variable on another. The data understanding part is crucial but without making any assumptions on the model form, the search space is super-exponential in the number of variables and therefore not a common practice.
**Result** We propose graphical hypergeometric networks (HNet), a method where associations across variables are tested for significance by statistical inference. The aim is to determine a network with significant associations that can shed light on the complex relationships across variables. HNet processes raw unstructured data sets and outputs a network that consists of (partially) directed or undirected edges between the nodes (i.e., variables). To evaluate the accuracy of HNet, we used well known data sets, and generated data sets with known ground truth by Bayesian sampling. In addition, the performance of HNet for the same data sets is compared to Bayesian structure learning.
**Conclusions** We demonstrate that HNet showed high accuracy and performance in the detection of node links. In the case of the Alarm data set we can demonstrate an average MCC score 0.33 + 0.0002 (P<1x10-6), whereas Bayesian structure learning showed an average MCC score of 0.52 + 0.006 (P<1x10-11), and randomly assigning edges resulted in a MCC score of 0.004 + 0.0003 (P=0.49). Although Bayesian structure learning showed slightly better results, HNet overcomes some of the limitations of existing methods as it processes raw unstructured data sets, it allows analysis of mixed data types, it easily scales up in number of variables, and allows detailed examination of the detected associations.

## Method overview
<p align="center">
  <img src="https://github.com/erdoganta/hnet/blob/master/docs/manuscript/figs/fig1.png" width="900" />
</p>

## Contents
- [Installation](#-installation)
- [Quick Start](#-quick-start)
- [Contribute](#-contribute)
- [Citation](#-citation)
- [Maintainers](#-maintainers)
- [License](#-copyright)

## Installation
* Install hnet from PyPI (recommended). Hnet is compatible with Python 3.6+ and runs on Linux, MacOS X and Windows. 
It is distributed under the Apache 2.0 license.

```
pip install hnet
```
* Alternatively, install hnet from the GitHub source:

```bash
git clone https://github.com/erdoganta/hnet.git
cd hnet
python setup.py install
```  

## Quick Start
- Import hnet method

```python
from hnet import hnet
```

- Simple example for the sprinkler data set
```python
df = pd.read_csv('https://github.com/erdoganta/hnet/blob/master/hnet/data/sprinkler_1000.csv')['close']
out = hnet.fit(df)
figHEAT = hnet.plot_heatmap(out)
figNETW = hnet.plot_network(out)
figD3GR = hnet.plot_d3graph(out)
```
<p align="center">
  <img src="https://github.com/erdoganta/hnet/blob/master/docs/manuscript/figs/fig2.png" width="900" />
</p>


```python
df=pd.read_csv('https://github.com/erdoganta/hnet/blob/master/hnet/data/titanic_train.csv')['Close']
out = hnet.fit(df)
figHEAT = hnet.plot_heatmap(out)
figNETW = hnet.plot_network(out)
figD3GR = hnet.plot_d3graph(out)
```
<p align="center">
  <img src="https://github.com/erdoganta/hnet/blob/master/docs/manuscript/figs/fig4.png" width="900" />
</p>

## Performance
<p align="center">
  <img src="https://github.com/erdoganta/hnet/blob/master/docs/manuscript/figs/fig3.png" width="900" />
</p>

## Citation
Please cite hnet in your publications if this is useful for your research. Here is an example BibTeX entry:
```BibTeX
@misc{erdoganta2019hnet,
  title={hnet},
  author={Erdogan Taskesen},
  year={2019},
  howpublished={\url{https://github.com/erdoganta/hnet}},
}
```

## Maintainers
* Erdogan Taskesen, github: [erdoganta](https://github.com/erdoganta)

## © Copyright
See [LICENSE](LICENSE) for details.
