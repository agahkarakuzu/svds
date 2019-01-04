## Description  

SVDS for visualizing a scatter plot linked to Lin's Concordance Correlation (LCC). 

## Format

| Family::Type | Correlation::Concordance |
|-----|----------------------------|

- [Tag](https://github.com/agahkarakuzu/svds/blob/master/Pearson.md#format)
    - OID
    - Subject 
    - Longitidunal
    - Segment 
- [Required](https://github.com/agahkarakuzu/svds/blob/master/Pearson.md#format)
     - xData     
     - yData     
     - xLabel    
     - yLabel
     - rhoConcordance
     - shiftedLine 
     - identityLine   
- [Optional](https://github.com/agahkarakuzu/svds/blob/master/Pearson.md#format)
     - CI        
     - CILevel    
     - pVal  
     - h          
     - shift
     - scale
     - biasFactor
     - CILine1    
     - CILine2    

## Details

LCC is a measure of absolute agreement between (continious) `xData` and `yData`. LCC coefficient ranges from -1 to 1 and indicates how well a measure compares to a gold standard (or to another metric that measures the same construct on the same scale).


### Tag

Please see [description.md](https://github.com/agahkarakuzu/svds/blob/master/description.md) for further details. 

| Key       | Type                    | Description of value                                       |
|-----------|-------------------------|------------------------------------------------------------|
| `OID`   | `<string>`|    'Correlation::Concordance'          |
| `Subject` | `<string>`|     SubjectID          |
| `Longitidunal`   | `<string>`|    LongitudinalID        |
| `Segment`   | `<string>`|    SegmentID        |

### Required

| Key        | Type                  | Description of value                                                                                |
|------------|-----------------------|-----------------------------------------------------------------------------------------------------|
| `xData`    | `<float>` `array [1XN]` | `N` number of data points or central tendency estimates for the first set of measurements.  |
| `yData`    | `<float>` `array [1XN]` | `N` number of data points or central tendency estimates for the second set of measurements. |
| `xLabel`   | `<string>`            | Nametag for `xData`                                                                                 |
| `yLabel`   | `<string>`            | Nametag for `yData`                                                                                 |
| `rhoConcordance` | `<float>`             | LCC coefficient                                                                                    |
| `deviationLine`  | `<float>` `array [1X4]` | Cartesian coordinates of two points that lie on the deviation line:`[x0,x1,y0,y1]`                   |
| `identityLine`  | `<float>` `array [1X4]` | Cartesian coordinates of two points that lie on the identity line:`[x0,x1,y0,y1]`              |

### Optional

| Key       | Type                    | Description of value                                       |
|-----------|-------------------------|------------------------------------------------------------|
| `pVal`      | `<float>`| The p-value associated with the LCC    |
| `h` | `<boolean>`        | Declares the significance of the LCC |
| `shift` | `<float>`      | The location shift |
| `scale` | `<float>`        | The scale shift|
| `biasFactor` | `<float>`        |  Measures how far the best-fit line deviates from the identity line. No deviation from the 45 degree line occurs when biasFactor equals 1.|
| `CI`      | `<float>` `array [1X2]` | LCC confidence interval: `[CI_lower,`CI_upper`]`          |
| `CILevel` | `<float>`               | Confidence interval level (1 - alpha). For example, 0.95.  |     
| `CILine1` | `<float>` `array [1X4]`  | Cartesian coordinates of two points that lie on the line belonging to the lower `CI`:`[x0,x1,y0,y1]` |  
| `CILine2` | `<float>` `array [1X4]`  | Cartesian coordinates of two points that lie on the line belonging to the upper `CI`:`[x0,x1,y0,y1]` |    

## Suggestions

- **Hover:**    To the nearest marker on the scatter cloud to display respective `xLabel`:`xData` and `yLabel`:`yData`.
- **Label:**    Display  `rConcordance`. If available, display upper and lower `CI`. Other optional values can be displayed if possible.
- **Fill :**    If available, fill between `CILine1` and `CILine2` with a transparent color.
