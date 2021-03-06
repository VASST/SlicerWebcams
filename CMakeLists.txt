cmake_minimum_required(VERSION 3.5)

project(SlicerPinholeCameras)

#-----------------------------------------------------------------------------
# Extension meta-information
set(EXTENSION_HOMEPAGE "https://github.com/VASST/SlicerPinholeCameras")
set(EXTENSION_CATEGORY "Cameras")
set(EXTENSION_CONTRIBUTORS "Adam Rankin (Robarts Research Institute), Elvis Chen (Robarts Research Institute)")
set(EXTENSION_DESCRIPTION "This extension contains modules for interacting with still and video cameras (calibration, capture, etc...)")
set(EXTENSION_ICONURL "https://github.com/VASST/SlicerPinholeCameras/raw/master/SlicerPinholeCameras_128.png")
set(EXTENSION_SCREENSHOTURLS "https://github.com/VASST/SlicerPinholeCameras/raw/master/Documentation/screenshot.png")
set(EXTENSION_DEPENDS "SlicerOpenCV;VASSTAlgorithms")
SET(EXTENSION_TAGS "NA")

#-----------------------------------------------------------------------------
# Extension dependencies
find_package(Slicer REQUIRED)
include(${Slicer_USE_FILE})

find_package(SlicerOpenCV REQUIRED)
mark_as_superbuild(SlicerOpenCV_DIR)

find_package(VASSTAlgorithms REQUIRED)
mark_as_superbuild(VASSTAlgorithms_DIR)

#-----------------------------------------------------------------------------
# Extension modules
add_subdirectory(PinholeCameras)
add_subdirectory(PinholeCameraCalibration)
add_subdirectory(PinholeCameraRayIntersection)
## NEXT_MODULE

#-----------------------------------------------------------------------------
include(${Slicer_EXTENSION_GENERATE_CONFIG})
include(${Slicer_EXTENSION_CPACK})
