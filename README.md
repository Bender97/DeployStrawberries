# Horticultural Temporal Fruit Monitoring via 3D Instance Segmentation and Re-Identification using Point Clouds

```
python3.8 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Install MinkowskiEngine
```
git clone https://github.com/NVIDIA/MinkowskiEngine.git
cd MinkowskiEngine
python setup.py install
```

## Instance Segmentation
```
export PYTHONPATH=$(realpath instance_segmentation)
cd instance_segmentation/mink_pan
python scripts/run_full_row.py --modelpath {PATH_TO_MODEL}
```

## Re-Identification
```
cd re_identification
python3 associate.py --iou 0.05
python3 extractor.py --iou 0.05
python3 train.py --mode testinst --data data/14_21_inst@0.05
```