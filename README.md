# dl_binder_design_RC
This repo provides usage instructions for setting up [dl_binder_design](https://github.com/nrbennet/dl_binder_design) on [Penn State's Roar Collab (RC) HPC system](https://www.icds.psu.edu/access-roar-and-roar-collab-online/).


### Installation


1. obtain a PyRosetta license from https://els2.comotion.uw.edu/product/pyrosetta
2. Download the `dl_binder_design` using `git clone https://github.com/nrbennet/dl_binder_design.git`, and create two dirs `pkgs` and `envs` along side with it.
3.  use the username and password of the newly obtained PyRosetta license to modify `~/.condarc` file, also modify the path of pkgs and envs to accommodate the large number and sizes of packages.
```
channels: 
- https://USERNAME:PASSWORD@conda.graylab.jhu.edu
- conda-forge
- defaults
pkgs_dirs:
  - /storage/icds/RISE/sw8/dl_binder_design/pkgs
envs_dirs:
  - /storage/icds/RISE/sw8/dl_binder_design/envs
```

4. navigate to <base_dir>/include and run `conda env create -f dl_binder_design.yml`
5. once `dl_binder_design` env is successfully installed and activate (`source activate /storage/icds/RISE/sw8/dl_binder_design/envs/dl_binder_design`), install `nvcc` module in conda for nvcc executables: `conda install -c "nvidia/label/cuda-11.3.0" cuda-nvcc`
6. Install `pandas`: `conda install pandas`
7. Naviate to <base_dir>/mpnn_fr
8.  Run `git clone https://github.com/dauparas/ProteinMPNN.git`
9.  Done!
