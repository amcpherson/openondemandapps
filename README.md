# openondemandapps
Open OnDemand Apps

clone into ~/ondemand/dev/ , ie:

```
git clone https://github.com/amcpherson/openondemandapps.git ~/ondemand/dev/
```

and then enable through the 'develop' button on the ondemand webapp.

## Jupyter

The Jupyter app requires an installation of jupyter in a conda environment.  Enter the name of the conda environment in which jupyter is installed in the `Conda Environment Name` config option.  Use the `Jupyter Binary` field to specify either `jupyter-lab` or `jupyter-notebook`.  Jupyter will launch in the `Notebooks directory` directory.

## RStudio

The RStudio app runs from an rocker based rstudio singularity image.

To build the singularity image first build a docker image on your local machine using:

```
cd $REPODIR/docker
docker build -t $DOCKERUSER/rocker-custom:latest -t $DOCKERUSER/rocker-custom:4.2.2 .
docker push $DOCKERUSER/rocker-custom:latest
docker push $DOCKERUSER/rocker-custom:4.2.2
```

Then build the singularity image with:

```
cd $SINGIMAGEDIR
singularity pull docker://$DOCKERUSER/rocker-custom:4.2.2
```

To run the app, enter `$SINGIMAGEDIR/rocker-custom_4.2.2.sif` into the `RStudio Singularity Image` field.  Also enter an existing directory into the `R packages` into which newly installed R packages will be stored.
