# Getting Started with AI on Jetson Nano

The power of AI is now in the hands of makers, self-taught developers, and embedded technology enthusiasts everywhere with the NVIDIA Jetson Nano Developer Kit. This easy-to-use, powerful computer lets you run multiple neural networks in parallel for applications like image classification, object detection, segmentation, and speech processing. In this course, you'll use Jupyter iPython notebooks on your own Jetson Nano to build a deep learning classification project with computer vision models.

You'll learn how to:

* Set up your Jetson Nano and camera
* Collect image data for classification models
* Annotate image data for regression models
* Train a neural network on your data to create your own models
* Run inference on the Jetson Nano with the models you create

Upon completion, you'll be able to create your own deep learning classification and regression models with the Jetson Nano.

This course can be found on https://courses.nvidia.com/courses/course-v1:DLI+S-RX-02+V2/about

## Running a Jetson nano headless

## This is specific to my system, you may need to change the IP address and Jetpack version.

**Connect to the ssh**

```
ssh shekharrv@192.168.1.25
```

**First time you need to create a folder**

```
mkdir -p ~/nvdli-data
```

**Run the Docker container**

```
sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --volume /tmp/argus_socket:/tmp/argus_socket \
    --device /dev/video0 \nvcr.io/nvidia/dli/dli-nano-ai:v2.0.1-r32.5.0
```

**To run reusable script with alternate CSI camera**

```
echo "sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --volume /tmp/argus_socket:/tmp/argus_socket \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.1-r32.5.0" > docker_dli_run.sh
chmod +x docker_dli_run.sh
./docker_dli_run.sh

```

## Logging into JupyterLab

* Open the following link address : 192.168.55.1:8888
The JupyterLab server running on the Jetson Nano will open up with a login prompt the first time.

* Enter the password: dlinano