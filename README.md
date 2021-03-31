# Regression - MLNET to ONNX

This sample trains an ML.NET regression model to predict the price of taxi fare based on features like trip distance, number of passengers, and payment type and then converts the model to ONNX format.
 
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


## Code to convert to ONNX
After training the ML.NET model with Fit() method, to convert to ONNX you will use the following code:

```csharp
using (var stream = File.Create("taxi-fare-model.onnx"))
                mlContext.Model.ConvertToOnnx(model, trainingDataView, stream);
```