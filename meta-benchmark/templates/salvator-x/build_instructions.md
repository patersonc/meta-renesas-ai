# How to build meta-benchmark for H3 Salvator-X
Currently only TensorFlow and TensorFlow Lite are supported.

## Check out meta-layers
```
git clone git://git.yoctoproject.org/poky
git clone git://git.linaro.org/openembedded/meta-linaro.git
git clone git://git.openembedded.org/meta-openembedded
git clone https://github.com/renesas-rcar/meta-renesas.git
git clone https://github.com/patersonc/meta-renesas-ai.git
```

## Check out correct revisions
```
pushd poky
git checkout 7e7ee662f5dea4d090293045f7498093322802cc
popd
pushd meta-linaro
git checkout 75dfb67bbb14a70cd47afda9726e2e1c76731885
popd
pushd meta-openembedded
git checkout 352531015014d1957d6444d114f4451e241c4d23
popd
pushd meta-renesas
git checkout ad3a8cfee5b6a6fab17cf1c6e5af851eaec75bd7
popd
pushd meta-renesas-ai
git checkout rcar-support
popd
```
## Source build env
```
source poky/oe-init-build-env
```

## Copy configuration files
```
cp meta-renesas-ai/meta-benchmark/templates/salvator-x/*.conf conf/
```

## Start build
```
bitbake core-image-minimal
```

The build output will be available in `tmp/deploy/salvator-x/`.
