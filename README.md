![alt text](svds2.png)

# Statistics Visualization Data Structure

This is a pet project aiming at describing a set of simple, yet useful, data structures that can facilitate generation of interactive figures and web-based visualization interfaces for statistical analyses performed on scientific data.

The idea is to decouple statistical computation from rendering of interactive/reactive features using Java Script Object Notation (.json) files, bringing following advantages:

* Increasing responsiveness of interactive operations  
* Providing cross-platform/language compatibility
* Reduction of the lie factor


### Preliminary list of methods

Each plot will be associated with a set of standard key-value pairs.


* Bland-Altman
* Intra class correlations
* Minimum detectable change
* Shift function
* Bootstrapped comparison of correlations
* Umbrella plots
* [Pearson](https://github.com/agahkarakuzu/svds/blob/master/Pearson.md)
* [Spearman](https://github.com/agahkarakuzu/svds/blob/master/Spearman.md)
* [Concordance](https://github.com/agahkarakuzu/svds/blob/master/Concordance.md)
* Skipped
* Percentage bend
* Bivariate descriptive
* Univariate descriptive  

### Study description

- Subjects
    - Number of Subjects (N)
    - Subject labels (string, 1XN)  
- Longitudinal    
    - Number of time points (Ntp)
    - Separation (string, 1X1)
         - Hour
         - Day
         - Week
         - Month
         - Year
    - Repeats per time point (int, 1XNtp)
- Group    
    - Number of grouping conditions (Ngp)
    - Name of grouping conditions (sting, 1XNgp)
    - Dependency of groups per each condition (sting, 1XNgp)  
         - Independent
         - Dependent
    - Number of subgroups per condition (int, 1XNgp)
    - Subgroup labels (string, NgpXNsgp)
    - Subject labels per subgroup (string, NgpXNsgp)
- Measure      
    - Number of measures (Nms)
    - Data type (int, 1XNms)
         - Nominal  [11]
         - Ordinal  [12]
         - Discrete [20]
         - Interval [21]
         - Ratio    [22]
    - Measurement method labels (string, 1XNms)
    - Metric labels  (string, 1XNms)
    - Units  (string, 1XNms)
- Measure.Segments
    - Availability per measure (logical, 1XNms)
    - Segment type
         - Tract
         - ROI
         - etc.
    - Number of segments (Nsg)
    - Segment labels     (string,1XNsg)
    - Segment indexes    (int,1XNsg)
