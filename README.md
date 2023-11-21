# Test JupyterDask Image

Create a custom image to run Jupyter and Dask using repo2docker and GitHub Actions.

Convert to SIF format and start Jupyter:

```shell
# convert image to SIF
apptainer build test-jupyterdask-image.sif docker://ghcr.io/fnattino/test-jupyterdask-image:latest
# run
apptainer exec \
  ./test-jupyterdask-image.sif \
  jupyter lab --no-browser --port=8888 --ip=0.0.0.0
```

Or in a single step:

```shell
apptainer exec \
  docker://ghcr.io/fnattino/test-jupyterdask-image:latest \
  jupyter lab --no-browser --port=8888 --ip=0.0.0.0
```
