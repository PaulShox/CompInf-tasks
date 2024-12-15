# **My Assignment Repository**

## Author: Paul O'Shaughnessy

## A Repository containing tasks and a project for the Computer Infrastructure module of the HDip in Data Analytics in ATU Galway

## ***Tasks***

There are a total of 9 tasks, using GitHub Codespaces, captured in this Repository. They are:

1. Create Directory Structure
Using the command line, create a directory named data at the root of the repository. Inside data, create two subdirectories: timestamps and weather.

2. Timestamps
Navigate to the data/timestamps directory. Use the date command to output the current date and time, appending the output to a file named now.txt. Make sure to use the >> operator to append (not overwrite) the file. Repeat this step ten times, then use the more command to verify that now.txt has the expected content.

3. Formatting Timestamps
Run the date command again, but this time format the output using YYYYmmdd_HHMMSS (e.g., 20261114_130003 for 1:00:03 PM on November 14, 2026). Refer to the date man page (using man date) for more formatting options. (Press q to exit the man page). Append the formatted output to a file named formatted.txt.

4. Create Timestamped Files
Use the touch command to create an empty file with a name in the YYYYmmdd_HHMMSS.txt format. This can be achieved by embedding the date command in backticks ` into the touch command. Redirection (>>) should not be used in this step.

5. Download Today's Weather Data
Change to the data/weather directory. Download the latest weather data for the Athenry weather station from Met Eireann using wget. Use the -O <filename> option to save the file as weather.json. The data can be found at this URL:
https://prodapi.metweb.ie/observations/athenry/today.

6. Timestamp the Data
Modify the command from Task 5 to save the downloaded file with a timestamped name in the format YYYYmmdd_HHMMSS.json.

7. Write the Script
Write a bash script called weather.sh in the root of the repository. This script should automate the process from Task 6, saving the weather data to the data/weather directory. Make the script executable and test it by running it.

8. Notebook
Create a notebook called weather.ipynb at the root of the repository. In this notebook, write a brief report explaining how Tasks 1 to 7 were completed. Provide short descriptions of the commands used in each task and explain their role in completing the tasks.

9.Pandas
In the weather.ipynb notebook, use the pandas function read_json() to load in any one of the weather data files downloaded by the script. Examine and summarize the data. Use the information provided data.gov.ie to write a short explanation of what the data set contains.

## ***Project***

* Automate the weather.sh script to run daily and push the new data to the repository. The following steps will create the necessary GitHub Actions workflow:

* Create a GitHub Actions Workflow: In the repository, create a folder called .github/workflows/. Inside this folder, create a file called weather-data.yml. This file will define the GitHub Actions workflow.

* Run Daily at 10am: Use the schedule event with cron to set the script to run once a day at 10am. Include also the workflow_dispatch event so the workflow can be tested.

* Use a Linux Virtual Machine In the workflow file, specify that a Ubuntu virtual machine should be used to run the action.

* Have the workflow clone to the repository.

* Add a step that runs the weather.sh script.

* Commit and Push Changes Back to the Repository.

* Test the Workflow Commit and push the workflow to the repository. 

