# Abductive Learning for Handwritten Equation Decipherment

This is the code repository of the abductive learning framework for handwritten
equation decipherment experiments in _Bridging Machine Learning and Logical
Reasoning by Abductive Learning_ in NeurIPS 2019.

## Environment dependency

**This code is only tested in Linux environment.**

1. Swi-Prolog
2. Python3 with Numpy, Tensorflow and Keras
3. ZOOpt (as a submodule)

### Install Swipl
[http://www.swi-prolog.org/build/unix.html](http://www.swi-prolog.org/build/unix.html)


### Install python3

<https://wiki.python.org/moin/BeginnersGuide/Download>

#### Install required package

```shell
#install numpy tensorflow keras
pip3 install numpy
pip3 install tensorflow
pip3 install keras
pip3 install zoopt
```

**Set environment variables(Should change file path according to your situation)**

```Shell
# cd to ABL-HED
git submodule update --init --recursive

export ABL_HOME=/home/wseng/ABL-HED
export LD_LIBRARY_PATH=$ABL_HOME/src/logic/lib
export SWI_HOME_DIR=/home/wseng/swipl/

# for GPU user
export LD_LIBRARY_PATH=$ABL_HOME/src/logic/lib:/usr/local/cuda:$LD_LIBRARY_PATH

```


#### Install Abductive Learning code

**First change the `swipl_include_dir` and `swipl_lib_dir` in `setup.py` to your own SWI-Prolog path.**

```Shell
cd src/logic/prolog
python3 setup.py install
```

## Demo for arithmetic addition learning

Change directory to `ABL-HED`, and run equaiton generator to get the training data

```shell
cd src/
python3 equation_generator.py
```

Run abductive learning code

```shell
cd src/
python3 main.py
```

or
```shell
python3 main.py --help
```

To test the RBA example, please specify the `src_data_name` and `src_data_file`
together, e.g.,

```shell
python main.py --src_data_name random_images --src_data_file random_equation_data_train_len_26_test_len_26_sys_2_.pk
```
## Authors

- [Wang-Zhou Dai](http://daiwz.net) (Imperial College London)
- [Yu-Xuan Huang](http://www.lamda.nju.edu.cn/huangyx/) (Nanjing University)
- [Le-Wen Cai](http://www.lamda.nju.edu.cn/cailw/) (Nanjing University)
