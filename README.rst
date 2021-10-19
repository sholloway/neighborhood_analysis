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