# flir_camera_driver

This repository contains packages for FlirImaging's line of cameras. This repositories intent is to make use of Flir's newly developed SDK: Spinnaker. The camera driver is an evolution of pointgrey_camera_driver. It has been updated to use the new methods provided by the SDK.

## Packages

### Spinnaker Camera Driver

The camera driver supports USB3 and GIGE cameras are planned. Note thats support for FireWire cameras is dropped in this SDK. The driver has been tested with a Blackfly S and Chameleon 3 camera. Differences between cameras requires that each camera model needs a customized interface class. If your camera type is not included, consider contributing the interface by referring to the section bellow.

### 

##### Contributing

Due to differences in parameter naming the configuration is separated from the main library. `camera.cpp` contains the base class `Camera` which can be extended to accommodate different cameras. The base class is based on BlackFly S and `cm3.cpp` extends it adding support for Chameleon3. To add a camera create a new derived class of `Camera` and add the model name to the check in `SpinnakerCamera::connect`.

To contribute to this repo, ensure your commits pass the linter pre-commit checks. To enable these checks you will need to install [linter](https://github.com/joshi-bharat/linter). We also provide a .clang-format file with the style rules that the repo uses, so that you can use [clang-format](https://clang.llvm.org/docs/ClangFormat.html) to reformat your code.

## Licence

This project is licensed under the BSD License - see the [LICENSE](LICENSE) file for details
