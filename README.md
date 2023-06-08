# conda-compiling-notes
Tips for building things from source inside conda

# Instructions and Tips
Use conda-forge for everything, (a mix of standard channel and conda-forge packages can cause problems)

`conda install -c conda-forge gxx_linux-64`
`conda install -c conda-forge cmake`
`conda install -c conda-forge make`
`conda install -c conda-forge gxx`

To update all packages that can be updated to conda-forge:
`conda upgrade -c conda-forge --all`

Move conda libs ahead of OS libs in `$LD_LIBRARY_PATH` to help address ld linker errors:
`conda env config vars set LD_LIBRARY_PATH=/home/bjohnson361-gtri/.conda/envs/ENV_NAME/lib:$LD_LIBRARY_PATH`

If you get issues with `GLIBC_x.x` not being found, try installing:
`conda install -c conda-forge sysroot_linux-64=x.x`

If you're having issues getting a package to install via conda-forge:
Try setting `channel_priority: strict` rather than `channel_priority: flexible` in your `.condarc`
