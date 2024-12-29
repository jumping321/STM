# Project Name: Synaptic Transmission Model of Drosophila

## Introduction

This project focuses on analyzing neuronal connections and calculating the weights between different types of neurons. The two primary notebooks in this repository, **`DRF_analysis.ipynb`** and **`ORF_analysis.ipynb`**, provide distinct analysis and calculation pipelines for analyzing the synaptic weights and patterns in neurons.

1. **`DRF_analysis.ipynb`**  
   This notebook is designed for performing the Depth-First Search (DFS) analysis on the neuron connections. It identifies and calculates the synaptic weights between different neurons, primarily focusing on the relationship between L2 neurons and LC11 neurons. The resulting data is stored in individual files, one for each LC11 neuron, detailing the total weights for L2 neurons it connects to.

2. **`ORF_analysis.ipynb`**  
   This notebook provides an alternate analysis pipeline, which may involve a different method for calculating or visualizing the synaptic relationships, possibly focusing on the orientation or receptor functionalities (ORF). It complements the DRF analysis by providing additional insights into the synaptic activity of neurons.

Both notebooks depend on the same input data files and will generate similar outputs, with each notebook focusing on a specific aspect of the neural connection analysis.

## File Structure

The project requires several input files and produces output files. Below is the description of the project directory structure:

### Input Files

These files need to be downloaded and placed in the `./data/` directory:

1. **`./data/classification.txt`**  
   - Contains the classification of neurons, including their `root_id`, `cell_type`, `side`, and `hemibrain_type`.
   - Example:
     ```plaintext
     root_id,cell_type,side,hemibrain_type
     123,L2,right,LC11
     456,LC11,right,LC11
     ...
     ```

2. **`./data/connections.txt`**  
   - Contains the connections between neurons, including the `pre_root_id`, `post_root_id`, `syn_count` (number of synapses), and `nt_type` (neurotransmitter type).
   - Example:
     ```plaintext
     pre_root_id,post_root_id,syn_count,nt_type
     123,456,10,GABA
     456,789,5,GLUT
     ...
     ```

3. **`./data/synapses.txt`**  
   - Contains the synaptic output information for each neuron. Each row corresponds to a neuron, containing its `root_id` and the `output synapses` (the number of synapses it sends out).
   - Example:
     ```plaintext
     root_id,output synapses
     123,15
     456,20
     ...
     ```

4. **Download Data**  
   - The input data files can be downloaded from [FlyWire Codex API](https://codex.flywire.ai/api/download).
   - After downloading, ensure that the files are named according to the structure above (e.g., `connections.csv` renamed to `connections.txt`) and are placed in the `./data/` directory.

### Output Files

Once the code is executed, the following output files will be generated in the `./result/LC11/L2_to_LC11/` directory:

1. **`LC11_neuron_id.txt`**  
   - For each LC11 neuron, a corresponding `.txt` file will be created. This file contains the total weights for all L2 neurons it connects to, based on the depth-first search (DFS) algorithm.
   - Example:
     ```plaintext
     L2_neuron_1: 0.12345
     L2_neuron_2: 0.56789
     ...
     ```

### Directory Structure

The final directory structure should look like this:

```plaintext
your_project_directory/
│
├── data/
│   ├── classification.txt
│   ├── connections.txt
│   └── synapses.txt
│
├── result/
│   └── LC11/
│       └── L2_to_LC11/
│           ├── LC11_neuron_id1.txt
│           ├── LC11_neuron_id2.txt
│           └── ...
│
├── DRF_analysis.ipynb
├── ORF_analysis.ipynb
├── T_ORF.ipynb
├── LC_Neuron_module.ipynb
├── LC_Neuron_module_looming.ipynb
└── README.md
```
## Requirements

To run the notebooks in this project, you will need to install the following Python packages:

- **pandas**: For data manipulation and analysis.
- **numpy**: For numerical operations and array handling.
- **tqdm**: For displaying progress bars during iterations.
- **matplotlib**: For creating visualizations and plots.
- **scipy**: For scientific and statistical computations.
- **warnings**: For handling warnings and suppressing future warnings during execution.

This README should now serve as a comprehensive guide for setting up and running the project. Let me know if you need any modifications!

