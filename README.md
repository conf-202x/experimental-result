
## Dataset and experimental resuslts
---
The repo contains the dataset for the paper.

### Dataset used in the paper for replication
---


There are ten folders in this repo, and each foler is named as the project name. Within each folder, it has the following structure:

```
├── parameters.txt
├── project
│   ├── url.txt
│   ├── raw_data.pkl
│   └── results
│       ├── basic
│       ├── ctx-ast
│       ├── ctx-ast-post-code
│       ├── ctx-logging
│       ├── ctx-ast-logging
│       └── ctx-post-code
```
0. `parameters.txt` contains all the parameters used in our model training.
1. The top level `project` is the folder contains all the data;
2. The second level `url.txt` contains the url to to dowanload the corresponding source code of the project from GitHub;  
3. `raw_data.pkl` contains the logging data extracted from the source code. The data can be eaisly assessed by using the following Python code:
```
import pickle

with open("raw_data.pkl", 'rb') as f:
    project_data = pickle.load(f)

# project_data is a list of list, it has the follwoing information:
# [[logging-id, filename, logging-statement, pre-log-code, post-log-code], ... ]
```

4. `results` contains all the translation results reported in our paper:
    - `basic` is the model for RQ1
    - `ctx-ast` is the model with the AST context
    - `ctx-ast-post-code` is  the model with both the AST and post-code context
    - `ctx-post-code` is the model with the post-code context
    - `ctx-logging` is the model with the logging context using multi-encoder.
    - `ctx-ast-logging` is the model with the AST and logging context using multi-encoder.
