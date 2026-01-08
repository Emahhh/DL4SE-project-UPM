# ConvNext-Tiny for Steel Defect Detection

Deep learning model for classification of steel defects using ConvNext-Tiny. 
This project helps detect defects on Ball Screw Drives.

## Quick Start

```bash
# Install dependencies
pip install -r requirements.txt

# Validate system
python code/validate_system.py

# Train with default config
python code/train.py

# Or run a sweep script to execute all combinations of hyperparameters defined in the script, with repetitions
./venv/bin/python code/experiments/run_hparam_sweep.py --help
```


## RunPod Setup

Quick RunPod workflow:

```bash
# 1. Clone on RunPod
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO

# 2. Run setup script
chmod +x setup_runpod.sh
./setup_runpod.sh

# 3. Start training
python code/train.py
```

## 📁 Project Structure

```
├── code/
│   ├── core/                 # Core modules
│   │   ├── models/          # ConvNext-Tiny + CBAM
│   │   ├── losses/          # Focal Loss, BCE
│   │   ├── data/            # Dataset, splitting
│   │   ├── augmentation/    # Image transforms
│   │   └── training/        # Trainer, callbacks, metrics
│   ├── train.py             # Training entry point
│   └── validate_system.py   # System validation
├── config/
│   └── train_config.yaml    # Hydra configuration
├── data/
│   ├── annotations/         # JSON annotations
│   ├── zips/               # Data archives (Git LFS)
│   └── images/             # Extracted images (not in git)
└── context/                 # Documentation
```


## Notes

- All parameters are in `config/train_config.yaml`
- The "data" folder must be properly initialized with the training data before starting the training scripts
