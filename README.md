# Download Voxceleb2
conda create -n voxceleb_trainer python=3.8
conda install --yes --file requirements.txt
pip install -r requirements.txt
conda activate voxceleb_trainer


Make sure all the files you want to download are listed in files.txt and fileparts.txt
(Might be found in finished.txt)

python ./dataprep.py --save_path ******* --download --user ********** --password *********




# VoxCeleb trainer

This repository contains the framework for training speaker recognition models described in the paper '_In defence of metric learning for speaker recognition_' and '_Pushing the limits of raw waveform speaker recognition_'.

### Dependencies
```
conda create -n voxceleb_trainer python=3.8
conda install --yes --file requirements.txt
conda activate voxceleb_trainer
```
`wget` and `ffmpeg` must be installed on the system, most likely using
```
sudo apt install ffmpeg
```
```
sudo apt install wget
```


### Voxceleb2 Download

To download Voxceleb2 first head to:
```
https://www.robots.ox.ac.uk/~vgg/data/voxceleb/
```
to get a username and password for permission to download the dataset.

You will likely fill in a form then a username and password will be sent immediately to your email.

Second, open lists/fileparts.txt and lists/finished.txt and make sure all files listed in finished.txt are also listed in fileparts.txt.

Note that you can either use 2 of these urls, depending on speed or availability
```
https://thor.robots.ox.ac.uk/~vgg/data/voxceleb/vox1a/FILE CHECKSUM
```
```
http://cnode01.mm.kaist.ac.kr/voxceleb/vox1a/FILE CHECKSUM
```

The following script can be used to download and prepare the VoxCeleb dataset for training.

```
python ./dataprep.py --save_path data --download --user USERNAME --password PASSWORD 
python ./dataprep.py --save_path data --extract
python ./dataprep.py --save_path data --convert
```




In order to use data augmentation, also run:

```
python ./dataprep.py --save_path data --augment
```






### Data

The [VoxCeleb](http://www.robots.ox.ac.uk/~vgg/data/voxceleb/) datasets are used for these experiments.

The train list should contain the identity and the file path, one line per utterance, as follows:
```
id00000 id00000/youtube_key/12345.wav
id00012 id00012/21Uxsk56VDQ/00001.wav
```

The train list for VoxCeleb2 can be download from [here](http://www.robots.ox.ac.uk/~vgg/data/voxceleb/meta/train_list.txt). The
test lists for VoxCeleb1 can be downloaded from [here](https://mm.kaist.ac.kr/datasets/voxceleb/index.html#testlist). 


### Citation

Please cite [1] if you make use of the code. Please see [here](References.md) for the full list of methods used in this trainer.

[1] _In defence of metric learning for speaker recognition_
```
@inproceedings{chung2020in,
  title={In defence of metric learning for speaker recognition},
  author={Chung, Joon Son and Huh, Jaesung and Mun, Seongkyu and Lee, Minjae and Heo, Hee Soo and Choe, Soyeon and Ham, Chiheon and Jung, Sunghwan and Lee, Bong-Jin and Han, Icksang},
  booktitle={Proc. Interspeech},
  year={2020}
}
```

[2] _The ins and outs of speaker recognition: lessons from VoxSRC 2020_
```
@inproceedings{kwon2021ins,
  title={The ins and outs of speaker recognition: lessons from {VoxSRC} 2020},
  author={Kwon, Yoohwan and Heo, Hee Soo and Lee, Bong-Jin and Chung, Joon Son},
  booktitle={Proc. ICASSP},
  year={2021}
}
```

[3] _Pushing the limits of raw waveform speaker recognition_
```
@inproceedings{jung2022pushing,
  title={Pushing the limits of raw waveform speaker recognition},
  author={Jung, Jee-weon and Kim, You Jin and Heo, Hee-Soo and Lee, Bong-Jin and Kwon, Youngki and Chung, Joon Son},
  booktitle={Proc. Interspeech},
  year={2022}
}
```

### License
```
Copyright (c) 2020-present NAVER Corp.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
