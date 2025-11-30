# ELITE
Data and code for ELITE E3 Ligase substrate Interaction Prediction using BERT.
ELITE: E3 Ligase Inference for Tissue specific Elimination: A LLM Based E3 Ligase Prediction System for Precise Targeted Protein Degradation
## Relevant files
1. ''ppi_finetuning.py'' tackles the finetuning and prediction for use case 1 ( tissue-specific ppi prediction)

## Prepare Conda Environment
1. Create the appropriate Conda env 
```
cd ~/git/STEP
conda env create -n STEP -f environment.yml
```
2. For GPU processing, install the correct pytorch package (see environment.yml for version and check out https://pytorch.org/get-started/previous-versions/ for specific commands)
```
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113
```
3. Activate Conda env
```
conda activate STEP
```

## Training a model
1. ''ppi_finetuning.py'': Use VSCode and run through the "Run and Debug" option.
```
cd ~/git/ELITE
conda activate ELITE

# set correct PYtHONPATH from the .env file, which is also used by VSCode
set -o allexport && source .env && set +o allexport  

# Print out all arguments
python src/ppi_finetuning.py --help

# Train a model
python src/ppi_finetuning.py --accelerator gpu --devices 2 --num_sanity_val_steps 0
```

## Manuscript to cite 

