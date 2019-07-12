# RLSS 2019: Pratical Sessions

## Personal commands

### With Docker

Start `docker desktop`. Then in `cmd`.

- `docker login`
- `docker pull yfletberliac/rlss2019-docker`
- `docker container ls`
- `// docker run -it -p 8888:8888 -v path/to/your/rlss2019-hands-on:/mnt/rlss2019-hands-on -d yfletberliac/rlss2019-docker`
- `docker run -it -p 8888:8888 -v C:\Users\simon.chauvin\Documents\private_GitHub\rlss2019-hands-on:/mnt/rlss2019-hands-on -d yfletberliac/rlss2019-docker`
- `docker container ls`
- `http://localhost:8888/tree/mnt/rlss2019-hands-on`

### Without Docker

For the two NN-based codes, `xdpyinfo was not found, X start can not be checked! Please install xdpyinfo!` when calling `display = Display(visible=0, size=(1400, 900))` and `display.start()`.

Working on Windows, I get troubles when trying to forward to views of `gym` envs. One option is to not show any behaviours. The other option is to execute the concerned notebooks out of `docker`.

I have created an `env` with anaconda and install the necessary packets as follows.

```anaconda
conda create --name rlss2019 python=3.6
conda activate rlss2019
nvcc --version
conda install pytorch torchvision cudatoolkit=9.0 -c pytorch
pip install Cython
pip install autopep8
python -m ipykernel install --user --name rlss2019 --display-name "rlss2019"
// gym
git clone https://github.com/openai/gym.git
cd gym
pip install -e .
pip install jupyter_contrib_nbextensions
conda install -c conda-forge opencv
conda install -c anaconda seaborn

jupyter notebook
// change kernel to rlss2019
```

We do not need display server anymore. Hence comment anything about `display = Display` or `PyVirtualDisplay`.

I can now run `DRL.01.REINFORCE+A2C_solution` and `DRL.02.DQN_solution`.

```anaconda
// for the rest of the notebooks (apart `TextWorld 101`)
pip install git+https://github.com/eleurent/highway-env
conda install -c conda-forge tqdm
```

## Setup and Installation

Two choices are available to you:

- running the notebooks on [Google Colab](https://colab.research.google.com) :orange_book: if you want to take advantage of the GPU acceleration it offers;
- running the notebooks elsewhere (locally or on a server).

### Google Colab

It has it's own VM so you only have to install the necessary packages from inside the notebooks.

### Elsewhere

You can use the `rlss2019-docker` image. [Here](setup.md) you'll find  the instructions for installing and running the `rlss2019-docker` image on Linux, MacOS or Windows.

## Materials

### Bandits

- [Stochastic Bandits](labs/MAB.Bandits.ipynb) [:orange_book:](https://colab.research.google.com/github/yfletberliac/rlss2019-hands-on/blob/master/labs/MAB.Bandits.ipynb)
- [Recommender Systems](labs/MAB.RecoSystems.ipynb) [:orange_book:](https://colab.research.google.com/github/yfletberliac/rlss2019-hands-on/blob/master/labs/MAB.RecoSystems.ipynb)

### Reinforcement Learning

- [Dynamic Programming + QLearning + SARSA](labs/RL.DP+QLearning+SARSA.ipynb) [:orange_book:](https://colab.research.google.com/github/yfletberliac/rlss2019-hands-on/blob/master/labs/RL.DP%2BQLearning%2BSARSA.ipynb)

### Deep Reinforcement Learning

- [REINFORCE + A2C](labs/DRL.01.REINFORCE+A2C.ipynb) [:orange_book:](https://colab.research.google.com/github/yfletberliac/rlss2019-hands-on/blob/master/labs/DRL.01.REINFORCE%2BA2C.ipynb)
- [DQN](labs/DRL.02.DQN.ipynb) [:orange_book:](https://colab.research.google.com/github/yfletberliac/rlss2019-hands-on/blob/master/labs/DRL.02.DQN.ipynb)
- [Model-Based](labs/DRL.03.ModelBased.ipynb) [:orange_book:](https://colab.research.google.com/github/yfletberliac/rlss2019-hands-on/blob/master/labs/DRL.03.ModelBased.ipynb)

### Final Project

--------

### Misc./Known issues

You are running Windows and want to install a Virtual Machine running Ubuntu 18.04? [Here](ubuntu-virtual-box.md) is a tutorial.
You may also want to directly [install](https://tutorials.ubuntu.com/tutorial/tutorial-ubuntu-on-windows#0) the Ubuntu terminal on Windows 10.

### Contributors

- Raphaël Avalos
- Geoffrey Cideron
- [Omar Darwiche Domingues](https://omardrwch.github.io/)
- [Yannis Flet-Berliac](https://ynns.io/)
- [Emilie Kaufmann](http://chercheurs.lille.inria.fr/ekaufman/)
- [Max Lapan](https://medium.com/@shmuma)
- [Edouard Leurent](http://www.edouardleurent.com/)
- [Odalric-Ambrym Maillard](http://odalricambrymmaillard.neowordpress.fr/)
- [Jérémie Mary](http://www.grappa.univ-lille3.fr/~mary/)
- [Mathieu Seurin](https://sites.google.com/view/mathieu-seurin/)
