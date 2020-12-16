# Exporting-Models-With-ONNX
This is a sample project that is meant to be imported into a Notebook (Jupyter) to see it in action. This sample is merely to provide an example of what the Notebook should look like when converting to an ONNX model. In this project, we use the CoreML model from the forked repository "YOLO-CoreML-MPSNNGraph."

The following command loads the CoreML Model from the forked repo:

coreml_model = coremltools.utils.load_spec('TinyYOLO.mlmodel')

The following command converts the CoreML into ONNX:

onnx_model = onnxmltools.convert_coreml(coreml_model, 'TinyYOLOv2')

The following command saves the ONNX Model:

onnxmltools.utils.save_model(onnx_model, 'tinyyolov2.onnx')

The following command displays the size of the file:

import os
print(os.path.getsize('tinyyolov2.onnx'))
