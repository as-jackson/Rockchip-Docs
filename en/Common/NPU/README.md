## RK3562/RK3566/RK3568/RK3588/RV1103/RV1106 RKNN SDK 1.6.0

### Major Modifications

- Support for ONNX models with OPSET from 12 to 19
- Support for custom operators (including CPU and GPU)
- Optimization of operator support such as convolution with dynamic weights, Layernorm, RoiAlign, Softmax, ReduceL2, Gelu, GLU, etc.
- Added support for Python 3.7/3.9/3.11
- Added the functionality of rknn_convert
- Improved support for transformers
- Optimization of MatMul API, such as increasing the K limit length, and new support for int4 * int4 -> int16 computation on RK3588, etc.
- Reduced initialization time and memory consumption for RV1106 rknn_init
- New support for some operators with int16 on the RV1106 platform
- Fixed random errors in convolution on the RV1106 platform under certain conditions
- Optimized user manual
- Refactored rknn model zoo, adding support for various models such as detection, segmentation, OCR, license plate recognition, etc.

### Version Query

- librknnrt runtime version: 1.6.0 (strings librknnrt.so | grep version | grep lib)

- rknpu driver version: 0.9.3 (dmesg | grep rknpu)

### Additional Information

- The rknn-toolkit is applicable to RV1109/RV1126/RK1808/RK3399Pro, while rknn-toolkit2 is suitable for RK3562/RK3566/RK3568/RK3588/RV1103/RV1106.
- The API interface of rknn-toolkit2 is fundamentally consistent with that of rknn-toolkit, requiring minimal modifications from the user (some parameters in the rknn.config() section have been reduced).
- The rknpu2 must be upgraded in sync with rknn-toolkit2 to version 1.6.0. rknn models generated with version 1.5.0 of the rknn toolkit2 do not need to be regenerated.
- Some demos within the rknn API depend on MPI MMZ/RGA, and they must be matched with the corresponding libraries in the system when used.

## RK3562/RK3566/RK3568/RK3576/RK3588 RKNN SDK v2.0.0-beta0

### Major Modifications

#### RKNN-Toolkit2 1.5.2

- Supports RK3576 (Beta version)
- Supports SDPA (Scaled Dot Product Attention), optimized transformer support
- Optimized matmul API
- Improved support for PyTorch/ONNX QAT models
- Added support for auto-generating C++ deployment code
- Supports PyTorch 2.1
- Enhanced support for operators such as Reshape, Transpose, BatchLayernorm, Softmax, Deconv, Matmul, ScatterND, etc.

### Version Query

- librknnrt runtime version: 2.0.0b0 (strings librknnrt.so | grep version | grep lib)
- rknpu driver version: 0.9.6 (dmesg | grep rknpu)

### Additional Information

- The rknn-toolkit is applicable for RV1109/RV1126/RK1808/RK3399Pro, while rknn-toolkit2 is suitable for RK3562/RK3566/RK3568/RK3576/RK3588/RV1103/RV1106.
- The API interface of rknn-toolkit2 is largely consistent with that of rknn-toolkit, requiring minimal modifications from users (some parameters in the rknn.config() section have been reduced).
- The rknpu2 must be upgraded in sync with rknn-toolkit2 to version 2.0.0b0. Customers who have previously used the rknn toolkit2 version 1.6.0 to generate rknn models do not need to regenerate them.
- Some of the demos within the rknn API depend on MPI MMZ/RGA; when using them, they must match the corresponding libraries in the system.