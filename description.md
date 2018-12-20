## Outline


Subjects  
NumberOfSubjects
SubjectIDs


Longitudinal
NumberOfTimePoints = [6,6,6,6,6,6,6,6...]
Separation          = [N/A, hour, day, week, year]
Repeats   = [1,1,1,1,1,1,1,1,...]

Group
NumberOfGroupingConditions: 3
NameOfGroupingConditions: {'Fever','Sex','Health'}
TypreOfDependency: {independent,independent, independent}
SubgroupsPerCondition: {2,2,2}
SubgroupNames: {{'high','low'},{'male','female'},{'healthy','sick'}}
SubjectsPerCondition: [['id']['id'],['id']['id'],['id']['id']]


Measure
NumberOfMeasures = 5
DataType         = [1xNumberOfMeasurements]
NameOfMeasure    = [1xNumberOfMeasurements]
NameOfMetrics    = [1XNumberOfMeasurements]
Units            = [SI,nu,np]   

DataTypes

Nominal   11
Ordinal   12
Discrete  20
Interval  21
Ratio     22

Measure.Segment  
SegmentAvailable =  [1 0 1 0 1] (1xNumberOfMeasurements)
SegmentType      =  ROI
SegmentID        =  [1XNSegments]
SegmentNames     =  [1XNSegments]
