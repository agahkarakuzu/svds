## Description  

SVDS for visualizing a scatter plot linked to a Pearson's product-moment correlation (PPMC) statistic.

## Format

| Class | Correlation::Pearson |
|-----|----------------------------|

- [Tag](https://github.com/agahkarakuzu/svds/blob/master/Pearson.md#format)
    - Class
    - Subject 
    - Longitidunal
    - Segment 
- [Required](https://github.com/agahkarakuzu/svds/blob/master/Pearson.md#format)
     - xData     
     - yData     
     - xLabel    
     - yLabel    
     - rPearson  
     - fitLine   
- [Optional](https://github.com/agahkarakuzu/svds/blob/master/Pearson.md#format)
     - CI        
     - CILevel    
     - pVal       
     - h          
     - slope      
     - intercept  
     - CILine1    
     - CILine2    

## Details

PPMC is a non-robust measure of linear association between `xData` and `yData`. To free the interpretation of the relationship between variables from p<0.05 comparison, `pVal` is described as an optional field.

### Tag

Please see [description.md](https://github.com/agahkarakuzu/svds/blob/master/description.md) for further details. 

| Key       | Type                    | Description of value                                       |
|-----------|-------------------------|------------------------------------------------------------|
| `Class`   | `<string>`|    'Bivariate::Pearson'          |
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
| `rPearson` | `<float>`             | PPMC coefficient                                                                                    |
| `fitLine`  | `<float>` `array [1X4]` | Cartesian coordinates of two points that lie on the best-fit line:`[x0,x1,y0,y1]`                   |

### Optional

| Key       | Type                    | Description of value                                       |
|-----------|-------------------------|------------------------------------------------------------|
| `pVal`      | `<float>`| The p-value associated with the PPMC          |
| `h` | `<boolean>`        | Declares the significance of the PPMC  |
| `slope` | `<float>`      | Slope of the `fitLine` |
| `intercept` | `<float>`        | Intercept of the `fitLine`|
| `CI`      | `<float>` `array [1X2]` | PPMC confidence interval: `[CI_lower,`CI_upper`]`          |
| `CILevel` | `<float>`               | Confidence interval level (1 - alpha). For example, 0.95.  |     
| `CILine1` | `<float>` `array [1X4]`  | Cartesian coordinates of two points that lie on the line belonging to the lower `CI`:`[x0,x1,y0,y1]` |  
| `CILine2` | `<float>` `array [1X4]`  | Cartesian coordinates of two points that lie on the line belonging to the upper `CI`:`[x0,x1,y0,y1]` |    

## Suggestions

- **Hover:**    To the nearest marker on the scatter cloud to display respective `xLabel`:`xData` and `yLabel`:`yData`.
- **Label:**    Display  `rPearson`. If available, display upper and lower `CI`. Other optional values can be displayed if possible.
- **Fill :**    If available, fill between `CILine1` and `CILine2` with a transparent color.
- **Callback:** PPMC is sensitive to the outliers. Markers can be selectively removed, then `fitLine` and `rPearson` can be updated to enable an interactive observation.
