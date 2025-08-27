# TabDiff easy run on just numerical features

## Environment Setup

Create the main environment with [tabdiff.yaml](tabdiff.yaml). Then update pytorch version xd.

```
conda env create -f tabdiff.yaml
conda activate tabdiff
pip install torch==2.5.0
```

## Dataset preparation

Save your tabular data as <NAME_OF_YOUR_DATASET>.csv file. 

**The first row should be the header** indicating the name of each column, and the remaining rows are records. Place you data's csv file in the directory named "datacsv".

Run the following command to process your dataset:
```
python process_dataset.py --dataname <NAME_OF_YOUR_DATASET>
```

## Training TabDiff and sampling

Config path: tabdiff/configs/tabdiff_configs.toml

model will generate a sample every ***check_eval_every*** epochs

To train a model across the entire table, run

```
python main.py --dataname <NAME_OF_DATASET> --mode train --exp_name <experiment_name>
```

Results will be saved in tabdiff/<NAME_OF_YOUR_DATASET>/<experiment_name>/
