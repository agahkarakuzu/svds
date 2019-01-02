## Subjects
    - Number of Subjects (N)
    - Subject labels (string, 1XN)  

## Longitudinal    
    - Number of time points (Ntp)
    - Separation (string, 1X1)
         - Null 
         - Hour
         - Day
         - Week
         - Month
         - Year
    - Repeats per time point (int, 1XNtp)

## Group    
    - Number of grouping conditions (Ngp)
    - Name of grouping conditions (sting, 1XNgp)
    - Dependency of groups per each condition (sting, 1XNgp)  
         - Independent
         - Dependent
    - Number of subgroups per condition (int, 1XNgp)
    - Subgroup labels (string, NgpXNsgp)
    - Subject labels per subgroup (string, NgpXNsgp)

## Measure      
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
    
## Measure.Segments
    - Availability per measure (logical, 1XNms)
    - Segment type
         - Tract
         - ROI
         - etc.
    - Number of segments (Nsg)
    - Segment labels     (string,1XNsg)
    - Segment indexes    (int,1XNsg)
