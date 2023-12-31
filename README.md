[![License](http://img.shields.io/:license-affero-blue.svg)](http://www.gnu.org/licenses/agpl-3.0.en.html) 

# Ka (nom a trouver)


## Goal

The aim of this pipeline is to launch multiple simulations of the stochastic simulation tool using the Kappa language: KaSim.
It also generates figures from the stimuli obtained previously.

## Composition

3 python files:

- launch.py
- graph_kasim.py
- utils.py

## Dependencies

- Python 3.8
- [Kappa](https://tools.kappalanguage.org/nightly-builds/)

## Use

Complete the graph_KaSim.ini file according to the instructions in the file. An example of the syntax is described for each parameter.
Launch the pipeline with the command 

```bash
python launch.py
```
### Simulation Parameter

- **KaSim**: absolute path toward KaSim exe
- **time**: Maximal time of simulation
- **input**: absolute path toward the kappa model
- **output**: absolute path for output files
- **log**: absolute path for log files
- **nb_jobs**: number of CPU used for the parallelization

- **variables**: list of variables to be modified (with variable names separated by ",", no spaces), can be empty
    - For each variable included in the list, specify its value(s) (separated by ",", no spaces) as described below:
    - *********************************exemple: 
        variables : nb_iterations,interval
        nb_interations: 6,8,9
        interval: 84*********************************

- **default_name_output:** default name of output file(s) if no variables are modified.

### Graph parameters

- **input_graph**: absolute path where the raw simulation files are stored
- **output_graph**: absolute path where graphs will be stored
- **graph_format**: format type for graphics, html, png, pdf jpeg, (default = png)
- **graph**: type of graphics required: medium, surface, 4D
- **surface_plot_variable_analysed**: name of the variable studied for the surface plot, CAUTION, this must be in the output file, so remember to plot it in your model!
- **timing**: time that can be extracted from the raw data, used for surface graphs and 4D
- **first_input_time**: 4
- **repetition**: number of times each simulation is run


## Warning

Be careful with the maximum number of jobs, by default the value is set at 4, above 6 simultaneous jobs, it is advisable to have more than 16GB of RAM.

