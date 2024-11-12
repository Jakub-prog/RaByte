

# Checks for Cuda,TensoRT and OpenCV

Here you can use the script for [[auto checks for CUDA, TensorRT, and OpenCV]]

### Manual Version Checks for CUDA, TensorRT, and OpenCV

#### 1. Check CUDA Version

To verify the installed version of CUDA:

```bash
nvcc --version
```

Look for a line that mentions `release`, e.g., `release 12.6`. This should match **12.6**.

If `nvcc` is not found, CUDA may not be installed.

#### 2. Check TensorRT Version

To check the version of TensorRT:

```bash
dpkg -l | grep -i tensorrt
```

The output will display TensorRT package names and their versions, such as `10.3.0.26`. Ensure this matches **10.3.0.26**.

If no output appears, TensorRT might not be installed.

#### 3. Check OpenCV Version (Python)

To check the version of OpenCV installed in Python:

```bash
python3 -c "import cv2; print(cv2.__version__)"
```

This command will output the OpenCV version.

If you see an error, OpenCV may not be installed or is not available in the Python environment.
