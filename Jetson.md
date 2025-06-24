# ml-env-setup for jetsonn nano

## for setup env for training

```Shell
sudo apt-get update
```

```Shell
sudo apt-get install git cmake libpython3-dev python3-numpy
```

```Shell
git clone --recursive https://github.com/dusty-nv/jetson-inference
```

```Shell
cd jetson-inference
```

```Shell
mkdir build
```

```Shell
cd build
```

```Shell
cmake ../
```

```Shell
make -j$(nproc)
```

```Shell
sudo make install
```

```Shell
sudo ldconfig
```
```Shell
pip3 install "numpy==1.24.4" --upgrade --no-deps
```
```Shell
sudo apt update
sudo apt install python3-opencv libopencv-dev -y
```

## for training own data

```Shell
docker/run.sh
```
in jetson orin 
Edit the file "run.sh" with your favorite text editor
Add the following line at line 187 and before 200

CONTAINER_IMAGE='dustynv/jetson-inference:r36.3.0'

```Shell
cd python/training/detection/ssd
```

```Shell
python3 train_ssd.py --dataset-type=voc --data=data/sauvc_flyer --model-dir=models/dummy --epochs=5 --workers=0 --batch-size=4
```

```Shell
python3 onnx_export.py --model-dir=models/dummy
```

```Shell
detectnet --model=models/dummy/ssd-mobilenet.onnx --labels=models/dummy/labels.txt --input-blob=input_0 --output-cvg=scores --output-bbox=boxes /dev/video0
```
