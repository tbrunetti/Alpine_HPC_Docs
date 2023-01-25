Use R version on SLURM Module Stack
====================================

R versions available
^^^^^^^^^^^^^^^^^^^^^
To use a pre-installed base R version on Alpine, you will need to view which R version to use first.  This can be done by running the following:  

1.  Request and start a compile node on Alpine  

.. code-block:: bash

    acompile  

.. image:: images/acompile_node.png
   :width: 1000

2.  Use the `module` command to view which versions of R are available:  

.. code-block:: bash

    module avail R/ 

.. image:: images/rversions.png
   :width: 800


Here you can see that there are two versions of R preinstalled on the cluster:  

* R/3.6.3  
* R/4.2.2

**If you require a different version that is not installed on the cluster, you will need to install the version you need yourself locally.**  We have provided a few options for you:

1. Installing R locally by following our instructions here  
2. Use Singularity to containerize your software locally and move the container into Alpine  
3. Use conda to build an R environment  


Using R
^^^^^^^

If you want to use R *interactively* in an R session follow the directions below:  

1.  Request and start a compile node on Alpine  

.. code-block:: bash

    acompile  

.. image:: images/acompile_node.png
   :width: 1000


2. Load in the R version from the stack that you want to use:  

.. code-block:: bash

    module load R/4.2.2 

3.  Start the R session:  

.. code-block:: bash

    R

.. image:: images/rsession_module.png
   :width: 800


**Alternatively**, if you want to use the R module in a batch script, you just need to add the module line to your batch script.  For example:  

.. code-block:: bash

    #SBATCH --nodes=1
    #SBATCH --partition=amilan
    #SBATCH --account=amc-general
    #SBATCH --time=01:00:00
    #SBATCH --memory=10G
    #SBATCH --log=myOutput%J.log
    #SBATCH --eror=myOutput%J.err
    
    module load R/4.2.2

    Rscript myRscript.R


Installing CRAN and Bioconductor packages
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
It is likely that you will need to install your own packages as right now our module stack only has `tidyverse` and `BiocManager` installed as packages.  In order to install your own libraries, follow these instructions:  

If you haven't already started an R interactive session, follow the directions listed above under the `Using R` section of the documentation.  Once you have started an R session, you can install the libraries you need as you normally would.  For example, let's try to install `data.table`.

1.  Install CRAN pacakges like you normally would in an interactive session:

.. code-block:: R

    install.packages("data.table")

You will see it automatically installs and places all of your R binary library files at the following path: `/projects/yourUserName/software/Rlibs`

2.  You can check your install of the package by loading the library in the R session:

.. code-block:: R

    library(data.table)

3.  If you wanted to install a Bioconductor library, you will need to just load the `BiocManager` library into your R session first.  For example, if we wanted to install the bioconductor package, `limma`, we would do the following:  

.. code-block:: R

    library(BiocManager)
    BiocManager::install("limma")



