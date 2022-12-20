# HPCC-Docs
In this repository you will find the documentation of the HPC resources available at the Università della Calabria


## Work locally
This documentation is build using [mkdocs](https://www.mkdocs.org/) and the [mkdocs-material](https://squidfunk.github.io/mkdocs-material/) theme.
When working locally on your machine you might want to check the changes in real time. To do so you will need to install mkdocs and the mkdocs-material theme. To do so, after cloning the repository, run the command:

``` 
python -m pip install -r requirements.txt 
```

or, if you have pip installed:

``` 
pip install -r requirements.txt 
```

We suggest that before doing so you create and activate a new python (or conda) environment. This is not mandatory, but it helps in keeping your system in good shape.
You can follow the steps below to create and activate a python/conda environment.
 
### Python

Create the environment
```	
python -m venv path/to/your/python/envs/<your_env_name>
```
Activate the environment
```
. path/to/your/python/env/<your_env_name>/bin/activate
```
Install mkdocs
```
python -m pip install -r requirements.txt 
```


### Conda
Create the environment and install mkdocs:
``` 
conda create --name <your_env_name> python>=3.10 pip>=21.0 -r requirements.txt
```
Activate the environment
```
conda activate <your_env_name>	
```


### Local deploment
Once you have mkdocs installed you can visualize  oyur changes. 
To do so go to the folder containing the `mkdocs.yml` file and run
```
mkdocs serve
```

You can now access your website at [http://127.0.0.1:8000/](http://127.0.0.1:8000/). The local web server will automatically reload after any change in a file of the documentation.

Enjoy and have fun!
 
