train -->  학습셋:camera1
train2 --> 학습셋:camera2

train4 -> crowdhuman으로 pre-training --> yolo detect train data=/abr/coss01/CrowdHuman_to_yolo/data/custom.yaml model=yolov8n.pt epochs=30 patience=5

train5 --> 데이터셋 합친걸로 모델 학습(pretrian x) yolo detect train data=/abr/coss01/camera/data/custom.yaml model=yolov8n.pt imgsz=1216 epochs=30 patience=5

train6 --> train4 (pre-training) 후 카메라 데이터셋 학습
yolo detect train data=/abr/coss01/camera/data/custom.yaml model=/abr/coss01/ultralytics/runs/detect/train4/weights/best.pt imgsz=1216 epochs=30 patience=5

train7 --> yolov8s, imgsz 1216, epochs 30, patience 5
