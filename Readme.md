# 🧫 DiCoLa: Divide-and-Conquer for Causal Structure Learning in the Presence of Latent Variables


This repository contains the reference implementation of the **DiCoLa** framework, as proposed in the paper *"A Recursive Decomposition Framework for Causal Structure Learning in the Presence of Latent Variables"*.

The core algorithm is implemented in [`DiCoLa/Recursive_PAG.py`](DiCoLa/Recursive_PAG.py), with the main entry point being the [`DiCola_learner`](DiCoLa/Recursive_PAG.py) function.


## 😀 Key Function

### `DiCola_learner`

**Parameters:**
- `observed_data` (`pd.DataFrame`): The input dataset provided as a pandas DataFrame with column names representing variables.
- `leaf_node_learner` (`callable`): A callable function (algorithm) used to learn the causal structures of leaf sub-problems.
- `alpha` (`float`): The significance level used for conditional independence (CI) tests.
- `ci_type` (`str`): The type of CI test to perform. Options include:
  - `'Fisher_Z'`: Fisher's Z test.
  - `'D_sep'`: Oracle CI test.

**Returns:**
- `dict`: A dictionary containing the learning results and some metrics:
  - `'PAG.DataFrame'`: The learned Partial Ancestral Graph (PAG) represented as a DataFrame.
  - `'CI_num'`: The total number of conditional independence tests performed.
  - `'runtime_sec'`: The total runtime of the method in seconds.

## Usage
Please refer to [`examples.py`](examples.py) for a complete demonstration of how to run the algorithm on sample data.


## Prerequisites & Requirements
The code is implemented in **Python 3.9.19** with the following dependencies:

- `numpy==1.26.4`
- `scipy==1.11.4`
- `pandas==2.2.2`
- `networkx==3.2.1`

## 🗒️ Notes

We will upgrade the code to be more compatible with any base algorithm. Please feel free to reach out if you have any questions or suggestions for improvement.

## 📝 Citation
If you use this code, please cite the following paper:

    @inproceedings{li2026recursive,
      title={A Recursive Decomposition Framework for Causal Structure Learning in the Presence of Latent Variables},
      author={Li, Zheng and Xie, Feng and Nie, Shenglan and Guo, Xichen and Wang, Ruxin and Zhang, Hao},
      booktitle={Proceedings of the Forty-third International Conference on Machine Learning},
      year={2026}
      }

