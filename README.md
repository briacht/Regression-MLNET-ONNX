# Regression - MLNET to ONNX

This sample trains an ML.NET regression model to predict the price of taxi fare based on features like trip distance, number of passengers, and payment type.
 
## NuGet Packages

Make sure to add:

- Microsoft.ML
- Microsoft.ML.OnnxConverter
- Microsoft.ML.OnnxTransformer
- Microsoft.ML.OnnxRuntime (for scoring)

## Transforms and trainers/algorithms

This pipeline contains the following transforms and trainers which are all ONNX exportable:

- OneHotEncoding transform
- Concatenate transform
- Light GBM trainer