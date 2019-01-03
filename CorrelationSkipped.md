## Description  

SVDS for visualizing a scatter plot linked to skipped correlation.  

## Format

| Class | Correlation::Skipped |
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
     - rSpearman 
     - outliers 
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

SRC is a non-parametric test of monotonic correlation between `xData` and `yData`. A monotonic bivariate relationship is characterized by a consistent increase/decrease in one of the independent variables, as the other variable increases (e.g. non-linear or logistic relationships).  

SRC can be applied to ordinal, interval or ratio data. It is based on ranks, therefore less sensitive to the outliers compared to the Pearson's product-moment. To free the interpretation of the relationship between variables from p<0.05 comparison, `pVal` is described as an optional field.

**Note:** `xData` and `yData` are ranked for this class. 

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
| `xData`    | `<float>` `array [1XN]` | `N` number of **ranked** data points or central tendency estimates for the first set of measurements.  |
| `yData`    | `<float>` `array [1XN]` | `N` number of **ranked** data points or central tendency estimates for the second set of measurements.|
| `xLabel`   | `<string>`            | Nametag for `xData`                                                                                 |
| `yLabel`   | `<string>`            | Nametag for `yData`                                                                                 |
| `rSpearman` | `<float>`             | SRC coefficient                                                                                    |
| `fitLine`  | `<float>` `array [1X4]` | Cartesian coordinates of two points that lie on the best-fit line:`[x0,x1,y0,y1]`                   |

### Optional

| Key       | Type                    | Description of value                                       |
|-----------|-------------------------|------------------------------------------------------------|
| `pVal`      | `<float>`| The p-value associated with the SRC         |
| `h` | `<boolean>`        | Declares the significance of the SRC |
| `slope` | `<float>`      | Slope of the `fitLine` |
| `intercept` | `<float>`        | Intercept of the `fitLine`|
| `CI`      | `<float>` `array [1X2]` | PPMC confidence interval: `[CI_lower,`CI_upper`]`          |
| `CILevel` | `<float>`               | Confidence interval level (1 - alpha). For example, 0.95.  |     
| `CILine1` | `<float>` `array [1X4]`  | Cartesian coordinates of two points that lie on the line belonging to the lower `CI`:`[x0,x1,y0,y1]` |  
| `CILine2` | `<float>` `array [1X4]`  | Cartesian coordinates of two points that lie on the line belonging to the upper `CI`:`[x0,x1,y0,y1]` |    

## Suggestions

- **Hover:**    To the nearest marker on the scatter cloud to display respective `xLabel`:`xData` and `yLabel`:`yData`.
- **Label:**    Display  `rSpearman`. If available, display upper and lower `CI`. Other optional values can be displayed if possible.
- **Fill :**    If available, fill between `CILine1` and `CILine2` with a transparent color.
