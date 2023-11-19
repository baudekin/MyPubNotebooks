*UNDER CONSTRUCTION*

# MyPubNotebooks

This is the site of my public notebooks for Julia usage. I'm was trained in applied mathematics along time go but used 
the training mainly as software developer not mathematician. The purpose of this site to provide examples of using Julia 
to preform statistical analysis based on the Jayne's statistical interpretation. Note there will be notebooks on using 
using Julia with linear algebra because I'm rusty and to do almost anything math related on computer you need to understand 
how to apply linear algebra. The resource links for putting this site together is at bottom of the page. 

## Install Juliaup and utilize it
I use Juliaup to mange my different versions Julia. Below is how install it on the Mac:

```
brew install juliaup
juliaup list
juliaup add 1.9.4
juliaup status
```
To utilize version 1.9.4 run:
```
julia +1.9.4 
```
or set the default version to 1.9.4:
```
julia default 1.9.4
julia
```
to update your installed version run:
```
juliaup update
```

## Install and run Juypterlab.

### Setup a project from juila project file under this github project.
```
cd ./MyLinearAlgerbra/
```
```
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
```
]
activate .
add IJulia
<delete>
jupyterlab()
install JupyterLab via Conda, y/n? [y]: y
```
### Define Kernel to use your project file.

To create juypterlab kernel for my Linear Algebra notes:
```
]
activate .
<delete>
using IJulia
IJulia.installkernel("MyLinearAlgerbra", "--project=./MyLinearAlgerbra")
```
### Launch juypterlab in current directory.

Start juypterlab based on the current Tom's Obvious Minimal Language (TOML) project file.  If you cd to ./MyLinearAlgerbra 
you will use the Project.toml located there.
Note the first time you run jupyterlab from julia it will prompt you to install it using Conda it will take a while.
Below is example of activating my MyLinearAlgerbra project.
```
cd ./MyLinearAlgerbra
```
```
]<enter>
activate .
<delete>
```
Below is how to start JupyterLab so it points to the notebooks located under ./MyLinearAlgerbra
```
using IJulia
jupyterlab(dir=pwd(), detached=true)
```

### Select Kernerl and notebook to run.

## Resource Links
* Juliaup Muliplexer for julia - https://github.com/JuliaLang/juliaup
* IJulia Julia-Language backend for Julia -  https://github.com/JuliaLang/IJulia.jl
* I can't work effecently without vi mode so I use jypterlab-vim: https://github.com/jupyterlab-contrib/jupyterlab-vim
* I perfer having a darkmode so I use: https://github.com/jupyterlab/jupyterlab_pygments
* Tom's Obvious Minimal Language - https://toml.io/en/


