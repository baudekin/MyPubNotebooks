*UNDER CONSTRUCTION*

# MyPubNotebooks

This is the site of my public notebooks for Julia usage. I was trained in applied mathematics along time go but used 
that training mainly as software developer not mathematician. The purpose of this site to provide examples of using Julia 
to preform statistical analysis based on the Jayne's statistical interpretation. Note there will be notebooks on using 
using Julia with linear algebra because I'm rusty and to do almost anything math related on computer you need to understand 
how to apply linear algebra. The resource links for putting this site together is at bottom of the page. 

## Install Juliaup and utilize it
I use Juliaup to mange my different versions Julia. Below is how install it on the Mac:

```zsh
brew install juliaup
juliaup list
juliaup add 1.9.4
juliaup status
```
To utilize version 1.9.4 run:
```zsh
julia +1.9.4 
```
or set the default version to 1.9.4:
```zsh
julia default 1.9.4
julia
```
to update your installed version run:
```zsh
juliaup update
```

## Install and run Juypterlab.

### Setup a project from juila project file under this github project.
```zsh
cd ./MyLinearAlgerbra/
```
```julia
]
activate .
instantiate
status
update
<delete>
```

### Install IJulia and Juypterlab for the first time.
If Juypterlab has not been installed for you system you will be prompted to install it
using miniconda. You will want to do that. Mini Python will installed in a sub directory under ~/.julia/conda
Note it will take a while to Jupyterlab.
```julia
]
activate .
add IJulia
<delete>
jupyterlab()
install JupyterLab via Conda, y/n? [y]: y
```
### Define Kernel to use your project file.

To create juypterlab kernel for my Linear Algebra notes:
```julia
]
activate .
<delete>
using IJulia
IJulia.installkernel("MyLinearAlgerbra", "--project=.")
```

The kernals on MacOS are stored under /Users/<user name>/Library/Jupyter/kernels. When you run installkernal command it creates a directy under
kernels directory. For example:

```zsh
├── kernels
│   └── mylinearalgerbra-1.9
│       ├── kernel.json
│       ├── logo-32x32.png
│       ├── logo-64x64.png
│       └── logo-svg.svg
```

To remove kernel just remove the directory aka mylinearalgerbra-1.9.  If you can't find the kernel directory fire up python env 
with juypter installed and run: /Users/<user name>/.julia/conda/3/aarch64/bin/jupyter --runtime-dir. Note you can also use the 
following juypter commands to manage your kernels:

```zsh
jupyter kernelspec list
jupyter kernelspec remove <kernel-name>
```


### Launch juypterlab in current directory.

Start juypterlab based on the current Tom's Obvious Minimal Language (TOML) project file.  If you cd to ./MyLinearAlgerbra 
you will use the Project.toml located there.
Note the first time you run jupyterlab from julia it will prompt you to install it using Conda it will take a while.
Below is example of activating my MyLinearAlgerbra project.
```zsh
cd ./MyLinearAlgerbra
```
```julia
]<enter>
activate .
<delete>
```
Below is how to start JupyterLab so it points to the notebooks located under ./MyLinearAlgerbra
```julia
using IJulia
jupyterlab(dir=pwd(), detached=true)
```

### Select Kernerl and notebook to run.
![image](https://github.com/baudekin/MyPubNotebooks/assets/585597/e56212ee-bea1-4051-a716-5b691f515a01)


### Diff Notebooks using git diff

```julia
pip install --upgrade pip
nbdime config-git --enable --global
```
Doing git diff will give you something like this:
![image](https://github.com/baudekin/MyPubNotebooks/assets/585597/3023cfdd-4017-47e8-b2d1-024cf978eea8)


## Resource Links
* Julia Setup and Packages
  * Julia - https://github.com/JuliaLang
  * Juliaup Muliplexer for julia - https://github.com/JuliaLang/juliaup
  * IJulia Julia-Language backend for Julia -  https://github.com/JuliaLang/IJulia.jl
  * Linear Algebra Julia Package - https://docs.julialang.org/en/v1/stdlib/LinearAlgebra/
  * Turing Julia Package - https://juliapackages.com/u/turinglang and https://github.com/TuringLang
  * Project file syntaz: Tom's Obvious Minimal Language - https://toml.io/en/
* Juypter Setup and Usage
  * I can't work effecently without vi mode so I use jypterlab-vim: https://github.com/jupyterlab-contrib/jupyterlab-vim
  * I perfer having a darkmode so I use: https://github.com/jupyterlab/jupyterlab_pygments 
  * Juypter Markdown and LaTex - https://saturncloud.io/blog/how-to-use-latex-in-jupyter-notebook/
  * LaTex Wiki - https://en.wikibooks.org/wiki/LaTeX
  * Notebook Diff Instructions - https://nbdime.readthedocs.io/en/latest/
* Bayesain Links:
  * [Statistical Rethinking A Bayesian Course with Examples in R and STAN By Richard McElreath](https://tertulia.com/book/statistical-rethinking-a-bayesian-course-with-examples-in-r-and-stan-richard-mcelreath/9780367139919)
  * [Probability Theory: The Logic of Science By  E. T. Jaynes ](https://tertulia.com/book/probability-theory-the-logic-of-science-e-t-jaynes/9780521592710)
  * [Bayesian Inference Videos](https://study.sagepub.com/lambert/student-resources/probability-the-nuts-and-bolts-of-bayesian-inference/author-videos)
  * [How to use Julia to perform Bayesian Analysis](https://storopoli.io/Bayesian-Julia/)


