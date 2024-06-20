# DVC - FOR PIPELINE TRACKING

<!-- # I am going to use the dvc for pipeline tracking
# Once I run the main.py (all the components is again and again)
# Data is downloading again and again
# That is the major issue, when we are doing the end to end projects, It will take some time, because it will train the model again and again
# It takes time
# Let say If everything is updated already, so why you will be training this again and again,
# Can we track this pipeline like the git we do

# So using DVC, Using that actually you can do the pipeline tracking, 
# so it will track the pipeline, so which pipeline you have actually executed and it is available or not

# If there is no change in any pipeline, so that particular step will be skip, and it will run the next component,
# If next component also not updated, it will move to next one.

# By using dvc, it will reduce your time and effort

# In first thing, which pipeline you are running
# First we are running our data ingestion pipeline, because this our first component and first pipeline -->

#### Once we created a dvc folder and files (pipeline) structure, we have to run the following commands in terminal DVC commands

# DVC Commands:

#### 1. Initialization

~ dvc init

(once we run this command, it will create a .dvc, .dvcignore file inside our project folder)

Then we have to run the dvc repro command, but before that we have to delete our artifacts folder, because, then only we can see that our pipeline will not be running again and again (which is already running)

#### 2. Repro

~ dvc repro

If you run this command, basically it will run the dvc.yaml file.
And, that dvc.yaml file will run our pipeline one by one

This command has worked, 
suppose, if first 2 components successfully running and raising any errors in 3rd components, 
once we solved that issue, if we run again this command, it is showing first 2 components skipping, because it is already running.
directly running the 3rd components.

#### Once the code running successfully, 
lets consider in artifacts folder I have deleted the (3 rd folder) prepare base model folder, 
then again I am running dvc repro command, 
now, I will get the prepare base model folder back, because I already runned.

## Until we did not change anything in code in any file, it will not running again and again, it will skipping everytime.
## If you run 1000 times, it will skip (for eg 2nd folder la endha changes um pannalana, second folder ah run pannadhu, direct a 3rd folder ku pogirum.)

#### So just try to do, whenever you are running your code, dont try to run the main.py, just try to run the dvc.yaml

#### 3. Dag

Dvc dag will show you the entire graph, (entire pipeline graph) in terminal.