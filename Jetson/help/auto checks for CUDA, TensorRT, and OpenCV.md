```bash
#!/bin/bash

# Check CUDA version
echo "Checking CUDA version..."
if command -v nvcc &> /dev/null
then
    cuda_version=$(nvcc --version | grep "release" | awk '{print $6}' | sed 's/,//')
    echo "CUDA version found: $cuda_version"
    if [[ "$cuda_version" == "12.6" ]]; then
        echo "CUDA version is correct (12.6)."
    else
        echo "Warning: CUDA version is $cuda_version. Expected 12.6."
    fi
else
    echo "CUDA is not installed."
fi

# Check TensorRT version
echo -e "\nChecking TensorRT version..."
if dpkg -l | grep -i tensorrt &> /dev/null
then
    tensorrt_version=$(dpkg -l | grep -i tensorrt | grep -oP '\d+\.\d+\.\d+\.\d+' | head -n 1)
    echo "TensorRT version found: $tensorrt_version"
    if [[ "$tensorrt_version" == "10.3.0.26" ]]; then
        echo "TensorRT version is correct (10.3.0.26)."
    else
        echo "Warning: TensorRT version is $tensorrt_version. Expected 10.3.0.26."
    fi
else
    echo "TensorRT is not installed."
fi

# Check OpenCV version
echo -e "\nChecking OpenCV version..."
if python3 -c "import cv2" &> /dev/null
then
    opencv_version=$(python3 -c "import cv2; print(cv2.__version__)")
    echo "OpenCV version found: $opencv_version"
else
    echo "OpenCV is not installed or not found in Python."
fi

```