# HPCC-Docs
In this repository you will find the documentation of the HPC resources available at the Università della Calabria


## Work locally
This documentation is build using [mkdocs](https://www.mkdocs.org/) and the [mkdocs-material](https://squidfunk.github.io/mkdocs-material/) theme.
When working locally on your machine you might want to check the changes in real time. To do so you will need to install mkdocs and the mkdocs-material theme. To do so, after cloning the repository, run the command:

```
python -m pip install -r requirements.txt
```
or simply

```
pip install -r requirements.txt
```

We suggest that before doing so you create and activate a new python (or conda) environment. This is not a strong requirement, but it helps in keeping your system in good shape.
You can follow the steps below to create and activate a python/conda environment.
 
## Results {.tabset}
### Python
	```
	python -m venv path/to/your/python/envs/<your_env_name>
	. path/to/your/python/env/<your_env_name>/bin/activate
	python -m pip install -r requirements.txt
	```
### Conda

	```
	conda create --name <your_env_name> python>=3.10 pip>=21.0 -r requirements.txt
	conda activate <your_env_name>	
	```



To visualize the changes you make in real time you can use `mkdocs`. To do so go to the folder containing the `mkdocs.yml` file and run
```
mkdocs serve
```

You can now access your website at [http://127.0.0.1:8000/](http://127.0.0.1:8000/). The local web server will automatically reload after any edit of a file in the documentation.
 
