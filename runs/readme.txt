train -->  �н���:camera1
train2 --> �н���:camera2

train4 -> crowdhuman���� pre-training --> yolo detect train data=/abr/coss01/CrowdHuman_to_yolo/data/custom.yaml model=yolov8n.pt epochs=30 patience=5

train5 --> �����ͼ� ��ģ�ɷ� �� �н�(pretrian x) yolo detect train data=/abr/coss01/camera/data/custom.yaml model=yolov8n.pt imgsz=1216 epochs=30 patience=5

train6 --> train4 (pre-training) �� ī�޶� �����ͼ� �н�
yolo detect train data=/abr/coss01/camera/data/custom.yaml model=/abr/coss01/ultralytics/runs/detect/train4/weights/best.pt imgsz=1216 epochs=30 patience=5

train7 --> yolov8s, imgsz 1216, epochs 30, patience 5
