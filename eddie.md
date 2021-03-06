[BPSM eddie](http://129.215.170.35/07_Using_Eddie.html)
[research service-eddie](https://www.wiki.ed.ac.uk/display/ResearchServices/Anaconda)
[igmm-Eddie3](http://wikilocal.igmm.ed.ac.uk/wiki/index.php/Cluster2-Eddie3)

# Logging In
ssh <YOUR UUN>@eddie.ecdf.ed.ac.uk
# Storage 
- home directory: 2GB backed up
/home/s1949868/
- "scratch" space: 2 TB for temporary files, they will be deleted after 1 month
/exports/eddie/scratch/s1949868/
> How to make use of them:
> 1.  Copy your dataset to the scratch space
> 2.  Complete your analysis
> 3.  Copy your results elsewhere
# Applications 
#see available modules
module available
#make modules available, by loading them
module load <MODULENAME/MODULEVERSION>
#see a list of currently loaded modules
module list
# Running Jobs 
shebang line
```bash
#!/bin/sh
```
Grid Engine options (lines prefixed with #$)
```bash
#$ -N hello              
#$ -cwd                  
#$ -l h_rt=00:05:00 
#$ -l h_vmem=1G
```
> give the queuing system (Grid Engine) information to schedule the job.
> cwd: run our script in its current working directory
> job name: -N
> use the current working directory: -cwd
> runtime limit: -l h_rt
> memory limit: -l h_vmem
> define where you want the outputs and errors to be sent: -o hello.o/-e hello.e

Initialise the environment modules
```bash
. /etc/profile.d/modules.sh
``` 
Load Python
```bash
module load python/3.4.3
``` 
Run the program
```bash
./hello.py
```
submit the job
```bash
# submit work to the cluster as batch jobs
qsub jobscript.sh
# guidance
man qsub
# queue status
qstat
# kill a job you have submitted
qdel 3246515
qdel Hello
# job info after finished
qacct -j 3246515
```
> The above included information on:
> when you ran your qsub command
> when this job was scheduled to run
> when it finished
> if it failed (if it fails, then "failed" would equal 1)
> the largest amount of memory it used (maxvemem)
# Array jobs
Identical jobs with the only difference being input parameters or data sets.
submit, stop and delete jobs with just one command.
submit an array job
```
qsub -t 1-100 job.array.sh data
```
Where job.array.sh looks like:
```
#!/bin/sh
# Grid Engine options (lines prefixed with #$)
#$ -cwd                 
#$ -l h_vmem=2G
 
job.sh $1.$SGE_TASK_ID
```
_-tc_ option in _qsub_ to limit the number of array task jobs running at any one time - keeping free some slots available for you to use for something else. For example:

 qsub -t 1-100 -tc 20 jobscript

will cause the 100 tasks to be run in batches of 20.
# Interactive Sessions 
#there are a limited number of nodes that accept interactive login sessions
#allow you to run interactive jobs or graphical applications. #to start an interactive session run:
qlogin
# Staging Data from DataStore 
#A subset of nodes have access to DataStore group spaces via NFS. 
#These nodes are intended for batch _and_ interactive jobs that copy data between DataStore and Eddie. 
#To send a job to these nodes, select the staging queue with the Grid Engine option `-q staging`. 
#For example, to get an interactive session run:
qlogin -q staging
# Monitoring Jobs 
#To query the status of your jobs
qstat
# login:
ssh -X s1949868@eddie.ecdf.ed.ac.uk
Lin&2019
VPN
# space
/home/s1234567/: 2GB
/exports/eddie/scratch/s1234567/: 2TB, **deleted after one month**
group's DataStore

You would:
1.  Copy your dataset to the scratch space
2.  Complete your analysis
3.  Copy your results elsewhere
# information for scheduling the job
#tell Eddie to run our script in its current working directory
#$ cwd
#specify the name of the job
#$ -N Hello
#**overestimate** the time and space needed
#Specify the amount of time the job will require .
#$ -l h_rt=00:01:00
#Specify the amount of memory needed: asking for 1GB RAM (default)
#$ -l h_vmem=1G
#define where you want the outputs and errors to be sent
#$ -o hello.o
#$ -e hello.e

# submit a job

# Others 
## Move files
scp [file you want to copy] [destination]
```bash
# Moving a file from bioinfmsc server to your home directory on Eddie 
scp myfavouritefile s1949868@eddie.ecdf.ed.ac.uk:/home/s1949868  
s1949868@eddie.ecdf.ed.ac.uk:/home/s1949868/
s1949868@eddie.ecdf.ed.ac.uk:/exports/eddie/scratch/s1949868/
s1949868@bioinfmsc4.med.ed.ac.uk:/home/s1949868
s1949868@bioinfmsc5.bio.ed.ac.uk
s1949868@bioinfmsc3.mvm.ed.ac.uk
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbOTA2OTIxODUzLC0xODY5Njc4NTY5LC0xMj
k4ODA4MDkyLC0xOTQ3MTU3NTY1LC0xNjgwNzcyMTA3LDEzODQ4
NjIxMjgsLTkxMTkxMjc1MywxMTEzMjA1Mzg2LDY1NjkyNzczNC
w4NDQ2NDc1MSwxNDA0Nzk2MzcyLDE4Mzc5Mjk2MzQsMTE4NDk2
MDI5MSw4ODg2MTM2NDgsMTY4NzMzMzIwOSwtMTE5MTA1NTkzOS
wxODQwMzI1Nzk1LDE5NzU3Mzc2NjcsLTQ2NTQ2MjQ1OCwtMTU2
ODU4MjE0MV19
-->