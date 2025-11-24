
# Dataset Description
The dataset comprises patches of size 512x512 pixels collected from Sentinel-2 L2A satellite mission. All reported forest fires are located in California.
For each area of interest, two images are provided: pre-fire acquisition and post-fire acquisition. Each image is composed of 12 different channels, collecting information from the visible spectrum, infrared and ultrablue.

The dataset is split into:
- train set
- validation set
- hidden test set, for which ground truth labels are not disclosed.

The hdf5 file is structured in this way:
```bash
root
|
|- uuid_0: {"post_fire", "pre_fire", "mask"}
| 
|
|- uuid_1: {"post_fire", "pre_fire", "mask"}
|
...
```
Each *uuid* have associated an attribute called *fold*.

Dataset can be downloaded from [here](https://hf.co/datasets/chabud-team/chabud-ecml-pkdd2023). You can find a script that can be used to load data.

Additional optional data are available [here](https://huggingface.co/datasets/chabud-team/chabud-extra). If you need more data, contact us.

# Evaluation
IoU is used for final evaluation. For the public leaderboard the data assigned to fold **0** are used for evaluation.

## How to submit
This is the code that can be used to create the encoding for a single prediction and the code to obtain the submission dataframe (to be exported as csv).

```python
import pandas as pd

from numpy.typing import NDArray
from trimesh.voxel.runlength import dense_to_brle
from typing import Literal, Dict


def compute_submission_mask(id: str, mask: NDArray):
    brle = dense_to_brle(mask.astype(bool).flatten())
    return {"id": id, "rle_mask": brle, "index": np.arange(len(brle))}

def obtain_submission_df(submissions: Dict[str, NDArray]) -> pd.DataFrame:
    res = []
    for uuid, prediction in submissions.items():
      submission_mask = compute_submission_mask(uuid, prediction)
      res.append(pd.DataFrame(submission_mask))
    return pd.concat(res)
```

The submissions must be in csv format with three columns: id, index, rle_mask. Remember to "explode" *index* and *rle_mask*, having a single value for each line. 
A sample submission creation can be found [here](https://huggingface.co/datasets/chabud-team/chabud-ecml-pkdd2023/blob/main/create_sample_submission.py).

You can find an example submission [here](https://huggingface.co/datasets/chabud-team/chabud-ecml-pkdd2023/blob/main/sample_submission.csv).


    
