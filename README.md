The tools makes use of the tool [code-mat](https://github.com/adamtornhill/code-maat) developed by Adam Tornhill. Follow the three steps described below.
## Step 1
Generate the git log for the repository you want to analyse. Go into the git repository you want to analyse and run the following command:
    
    git log --all --numstat --date=short --pretty=format:'--%h--%ad--%aN' --no-renames > <your_file_name>

Save the result in a file.

## Step 2
Next, use code-maat to anaylse the log you generated in step one. In the repository you'll find a runnable jar file of code-maat. Go into the tool's repository and enter the folder "code-maat". Execute the following command:
    
    java -jar code-maat.jar -l <path_to_file_from_step_1> -c git2 -a coupling > <your_file_name>

Save the result in a file. 

## Step 3
Go into the tool's repositoy and run the tool with the following command:
    
    python3 tool.py <path_to_file_from_step_2>

The rendered diagram is found in the folder "rendered". If you set up a default pdf viewer, it should open automatically.