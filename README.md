# Twin Cities Neighborhood Analysis
- - -

**Process**
1. Try to identify the main questions I want to ask of the data.  
2. Find the various datasets that may help answer the questions.   
3. Some data is tabular. Some data is spatial. Consolidate the tabular using a 
   spreadsheet app.  
4. Identify the tools to use for the actual analysis. In this case they are:
  - Language: Python
  - Environment: Jupyter Notebooks, VSCode
  - Dependency Management and Build Lifecycle: poetry
  - In memory data storage: Using a data structure called a _dataframe_. 
      The most popular dataframe for Python based data analysis is _pandas_. 
      I'm using a geospatial extension to Pandas called _geopandas_. This adds the 
      ability to work with common spatial file types and operations.
  - Visualization: ?


Dealing with Data Lessons
- Merging dataframes screws the return type up unless you use Pandas's merge function 
  with the geospational DF as the left table.
- Merging strips the geometry if they geometries doen't align in two geospatial 
  dataframes. A work around is to load non-spatial data with a Pandas dataframe.



**Resources**
- [Real Estate Data](https://www.realtor.com/research/data)
- [Shape Files](https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html)

- - -
## Working with the repo.
This project leverages poetry for dependency management. It creates a
virtual environment to run everything in.

## Local Development

1. Git Clone the project.
2. Configure poetry to create the virtual environments on the project path.
   This is required if you want to use VSCode to work with the notebooks.

```shell
poetry config virtualenvs.in-project true
```

2. Install the dependencies with poetry. This creates the virtual environment
   in .venv in the project. Make sure this is ignored by git.

```shell
poetry install --no-root
```

3. Launch a shell to do work in.

```shell
poetry shell
```

4. Inside the shell launch Jupyter Notebooks.

```shell
jupyter notebook
```

### Developing with VSCode

VSCode has the ability to work with Jupyter Notebooks.
To do so requires a little setup.

1. Make sure you're using the latest version of VSCode.
2. Install the Jupyter extensions for VSCode. You need this for the IpyWidgets.
3. Set the path to the virtual environment in VSCode.
   Code -> Preferences -> Settings
   Search for the setting python.venvPath. _Python: Venv Path_ should appear.
   Set it to be ./venv
4. Restart VSCode.
5. After restarting, when trying to select a Kernel to run the notebook
   the ./venv should now be in the menu to pick. Select that one.

Now you should be able to run the notebook. If you get an error message that looks like this:

> Widgets require us to download supporting files from a 3rd party website. (Error loading ipycanvas:^0.9.0).

What's happening is that the ipycanvas module is trying to download from https://unpkg.com/ipycanvas@^0.9.0/dist/index
Enable this by clicking the button on the popup allowing the download. You'll have to reload the extension to get the change to take effect.