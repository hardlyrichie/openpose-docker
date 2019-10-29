# openpose-realsteel
Based off of https://github.com/ExSidius/openpose-docker, but includes Python API and COCO Model support

Dockerfile to build OpenPose from CMU

Ensure that you have [`nvidia-docker`](https://github.com/NVIDIA/nvidia-docker#quickstart) installed before you download this image.

To run the container, use the following commmand - 

```bash
xhost +
docker run -it --net=host -e DISPLAY -e QT_X11_NO_MITSHM=1 --runtime=nvidia --device=/dev/video0:/dev/video0 <image-id>
```

To run the webcam demo, use

```
./build/examples/openpose/openpose.bin --model_pose COCO --net_resolution "-1x160"
```

As Olin Laptops have 2005MB of GPU memory and therefore need to use the COCO model at a lower net resolution.

Check with `nvidia-smi`.

Uses: CUDA 10, CUDnn 7
