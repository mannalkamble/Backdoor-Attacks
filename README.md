# Backdoor Detector for BadNets

This project involves designing a backdoor detector for neural networks known as BadNets, specifically trained on the YouTube Face dataset. The detection is based on the pruning defense strategy. The detector prunes the last pooling layer of a backdoored BadNet and analyzes if a test input is clean or backdoored.

## Project Description

This backdoor detector operates by comparing the outputs of the original BadNet (B) and a pruned version of the network (B'). If their outputs for a test input agree, the input is classified as clean. If the outputs disagree, the input is classified as backdoored. The system utilizes a pruning defense where channels in the last pooling layer are removed in descending order of their activation values until the validation accuracy drops by a specified percentage.

## Prerequisites

Before you can run the Jupyter Notebook, ensure you have the following installed:
- Python 3.6 or newer
- PyTorch
- NumPy
- Matplotlib (for generating plots)
- Jupyter Notebook

## Setup

Clone the repository and install the required Python packages:

```bash
git clone https://github.com/mannalkamble/Backdoor-Attacks.git
cd Backdoor-Attacks
```

## Usage

To run the detector, open the Jupyter Notebook in this repository:

```bash
jupyter notebook Backdoor Attacks.ipynb
```

Follow the instructions within the notebook to specify the prune percentage (e.g., 2%, 4%, 10%) and run the cells to execute the detection process.

## Evaluating the Model

To evaluate the repaired networks, use the provided `eval.py` script, which can be found in the "lab3" directory of the CSAW-HackML-2020 GitHub repository.

```bash
python eval.py --model_path path_to_your_model
```

## Results

After running the evaluation script, you will get the accuracy on clean test data and the attack success rate on backdoored test data as a function of the fraction of channels pruned. These results can be found in the report.
