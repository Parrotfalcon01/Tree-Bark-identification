# Tree-Bark-identification

This project is a attmpt to get a AI to identify 20 diffrent types of tree bark and get it to out put what it thinks the awnser is 
the key to it is:
```bash
'BOJ' : Yellow birch",
'BOP' : White birch",
'CHR' : Northern red oak",
'EPB' : White spruce",
'EPN' : Black spruce",
'EPO' : Norway spruce",
'EPR' : Red spruce",
'ERR' : Red maple",
'ERS' : Sugar maple",
'FRA' : White ash",
'HEG' : American beech",
'MEL' : Tamarack",
'ORA' : American elm",
'OSV' : American hophornbeam",
'PET' : Quaking aspen",
'PIB' : Eastern white pine",
'PIR' : Red pine",
'PRU' : Eastern Hemlock",
'SAB' : Balsam fir",
'THO' : Northern white cedar",
```

![add image descrition here](direct image link here)

## The Algorithm

the training happend over 100 cycles over that time it was improving its self at the end of the training it had 96% accuracy with a training set of roughly 4000 images 

to run this project I downloded the data set at https://www.kaggle.com/datasets/claudecoulombe/barknet-mini i then unziped it and ran the docker by using: ./docker/run.sh once inside run this to change directories so you are in: cd python/training/classification from there you can run the training script to train the network: python3 train.py --model-dir=models/BarkNet-mini/BarkNet-mini once that is done you should export it as a onnx using this command: python3 onnx_export.py --model-dir=models/BarkNet-mini Set the NET and DATASET variables: NET=models/BarkNet-mini  DATASET=data/BarkNet-mini run this to test it: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/one of your catagories/image name.jpg Output.jpg 

the libraries installed were python3-numpy

[View a video explanation here](video link)
