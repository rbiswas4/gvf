# Validation Framework

The objective is to develop a convenient framework where we can compare population distribution of objects in simulated catalogs to population distributions in previous observations or previous catalogs.

Thus we want 
- summary statistics to compare the populations in two or more catalogs
- visualization of population distributions or slices in two or more catalogs

This may be more generally useful beyond galaxy simulation task force, and may be useful for comparing other astrophysical objects.

## Efficient Summaries of Populations

It is possibly useful if we 
- enumerate as many kinds of statistics / visualizations that we may want as part of the validation framework.
- enumerate the structure of catalogs that we expect


### The datasets: Catalogs
- Likely to be (lists of) (2D) table format: summary of different object properties (example halo catalog of MB in nersc) which are halo catalogs at different times.
- Tree/graph structure: Example(consider the collection of particles forming the halos and their spatial positions or the the halos in time)

### Calculations we would like to do

(Mostly thinking of the table data)

Comparison to previous data would be of the following types:
- Comparison of the relation of two quantities against each other, perhaps after selecting a subset of the population. It should be easy to do this for any pair of variables in the table or functions thereof. More specifically, the plots would be 
    - mean values of the variables with error bars
    - heatmaps (or with smoothing) contour plots
- Comparison of the distribution function of a single variable. Essentially histograms. Again, we should be able to map theseto functions of the variable.

- Spatial statistcs (like correaltaion functions) on restiricted variables. 

### Formats:
- maybe we should agree on a particular internal representation, but not necessarily a file format. 
- The internal representation could be read in from a few different formats on disk and written out to the same formats. Examples are hdf (portable), csv (because everyone will be abe to read), database (most flexible, amenable to above calculations).
- Units: We can decide now, but would also be useful to consider schemes like 
`astropy.qunatity`. Here every physical quantity is a Quantity rather than a float or integer. The quantity has an attribute unit where one can specify one of the known sensible (according to dimensions0 units for the object. Then when a second unit comes in, the quantity is transformed accordingly.
