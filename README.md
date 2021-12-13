# Artifact: Static Analysis of Enterprise Applications: Frameworks and Caches, the Elephants in the Room

This is a duplication of the artifact for the paper "Static Analysis of Java Enterprise Applications: Frameworks and Caches, the Elephants in the Room" (PLDI '20).

The origianl artifact provided by the authors of the paper can be found here: https://doi.org/10.5281/zenodo.3742711


# Analysis results

The results of the experiment have been obtained by running the analysis on the machine with the following **hardware specifications**:

**CPU:** Intel® Xeon® Platinum 8272CL (second-generation Intel® Xeon® Scalable processor.) This custom processor runs at a base speed of 2.5 Ghz and can achieve up to 3.4 Ghz all core turbo frequency. 8 vspus (virtual CPUs).

**RAM:** 64 GiB

**SSD:** 512 GB

**Operating System:** Ubuntu 20.04.3 LTS


I was able to successfully reproduced the results for **Figure 4.  App methods reachability for Doop and JackEE** and **Table 1. Precision+speed metrics**.


# Running the Artifact

First, proceed to the authors' artifact page (https://doi.org/10.5281/zenodo.3742711) and download `jackee-artifact.tar`. 
Once the actual artifact is downloaded, you can run the analysis by following the instructions below. These instructions were taken from the authors artifact page. I decided not to change anything in their instructions as I was able to successfully run the artifact with the help of their step-by-step guide.

## Step-by-step Guide

The name of the docker image archive is `jackee-artifact.tar`.

Start a tmux session with two windows. In the first window, run the following commands:

```bash
docker load -i jackee-artifact.tar
```

This command will load an image named `jackee-zenodo-artifact:1.0`.

The next step is to start a docker container from the image with the following command:

```bash
docker run --name jackee-artifact --it jackee-zenodo-artifact bash
```

Using an interactive shell and the *-it* option is not necessary but it may be helpful in case you want to add any utility programs to the container.

After that you need to login to the container with the command:

```bash
docker exec -it --user pldi2020 jackee-artifact bash
```

This command will log you in as the `pldi2020` user in the root directoy. Please run:

```bash
cd /home/pldi2020/
```

to switch to the home directory of the `pldi2020` user.

Next please untar the pre-existing facts using the `untar-facts.sh` script:

The environment should be all set, but in order to run an analysis it is necessary to untar the facts first. To do that please run:

```bash
./untar-facts.sh
```

The artifact includes the facts (i.e., the analyzed program, preprocessed in database form) in the artifac. The two archives `benchmark-facts.tar.gz` and `benchmark-modified-facts.tar.gz` are about 1.8GB. The untarred fact directories `/home/pldi2020/benchmark-facts` and `/home/pldi2020/benchmark-facts` are about 30GB each, thus the compression step was necessary.

The authors also included two scripts `./create-facts.sh` and `./create-modified-facts.sh`. The former script can be run with the command: 
```bash
./create-facts.sh <benchmark-name>
```

The script will process the benchmark jars under `/home/pldi2020/benchmark-jars/<benchmark-name>/` and produce the specified benchmark's facts under `/home/pldi2020/benchmark-facts/<benchmark-name>/` overwriting any pre-existing facts under this directory.

The latter script can be run with the command:

```bash
./create-modified-facts.sh <benchmark-name>
```

The script will process the benchmark jars under `/home/pldi2020/benchmark-jars/<benchmark-name>/` and produce the specified benchmark's facts under `/home/pldi2020/benchmark-modified-facts/<benchmark-name>/` overwriting any pre-existing facts under this directory.


### Running a Single Benchmark

### **context-insensitive analysis**

From the home directory of user `pldi2020` you can execute:

```bash
./runSingleCIBench.sh <benchmark-name>
```

The available benchmark names are ***alfresco***, ***bitbucket-server***, ***dotCMS***, ***opencms***, ***shopizer***, ***SpringBlog***, ***pybbs***, ***WebGoat***.

By running `./runSingleCIBench WebGoat` JackEE will run a context-insensitive analysis on the facts found at `/home/pldi2020/benchmark-facts/WebGoat-facts` and the `print-metrics.py` script will also print them on your terminal and create the file `/home/pldi2020/WebGoat-context-insensitive-metrics.txt`.

For instance, the printed metrics for a context-insensitive analysis of ***WebGoat*** are the following:

execution time: 39s
avg. objs per var: 34.2
avg. objs per app var: 14.1
edges (over 12242 reachable methods): 71666
app polymoprhic virtual calls (of 2219 reachable app virtual call sites): 103
app reachable casts that may fail (of 56 reachable app casts): 49
% of app reachable methods over app conrete methods: 50.6

This is the format of output for all types of analyses described below.

### **2-object-sensitive+heap analysis**

From the home directory of user `pldi2020` you can execute:

```bash
./runSingle2ObjBench.sh <benchmark-name>
```

The available benchmark names are ***alfresco***, ***bitbucket-server***, ***dotCMS***, ***opencms***, ***shopizer***, ***SpringBlog***, ***pybbs***, ***WebGoat***.

### **modified 2-object-sensitive+heap analysis**

From the home directory of user `pldi2020` you can execute:

```bash
./runSingleMod2ObjBench.sh <benchmark-name>
```
The available benchmark names are ***alfresco***, ***bitbucket-server***, ***dotCMS***, ***opencms***, ***shopizer***, ***SpringBlog***, ***pybbs***, ***WebGoat***.
