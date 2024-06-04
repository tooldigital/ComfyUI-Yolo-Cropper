# ComfyUI-Yolo-Cropper

A very simple node to help you create image crops and masks using YoloV8.

It is usefull for creating square crops when working with controlnets, ip-adapters etc that need 1:1 ratio input like 1024x1024 for example.

It uses YoloV8 - [Ultralytics](https://github.com/ultralytics/ultralytics) - with COCO 80  objects for detection added with a specific feature for face detection.

All necessary models will be downloaded automatically at first use.
- https://github.com/ultralytics/assets/releases/download/v8.2.0/yolov8l.pt
- https://huggingface.co/spaces/cc1234/stashface/resolve/main/.deepface/weights/yolov8n-face.pt


![image](https://raw.githubusercontent.com/tooldigital/ComfyUI-Yolo-Cropper/main/img/cropper_image.png)


### Input

- image = Any input image will do
- object = dropdown list with COCO 80 objects, it has face as en extra.
- padding = padding that is added to the square crop (not the orginal crop)

### Output

- bounding box = array of values x,y,width,height
- image yolo detections = an image showing all detected assets and bounding boxes
- image original crop = the image cropped according the actual bounding box
- image square crop = the image cropped according a square bounding box starting from the center of the original bounding box
- mask orginal crop = a black and white mask cropped according the actual bounding box
- mask square crop = a black and white mask cropped according a square bounding box starting from the center of the original bounding box

### Basic flow with face and person

![image](https://raw.githubusercontent.com/tooldigital/ComfyUI-Yolo-Cropper/main/img/workflow_1.png)

### Basic flow with object - parking meter

![image](https://raw.githubusercontent.com/tooldigital/ComfyUI-Yolo-Cropper/main/img/workflow_2.png)

### Flow using IP-Adapter FaceID

![image](https://raw.githubusercontent.com/tooldigital/ComfyUI-Yolo-Cropper/main/img/workflow_3.png)

