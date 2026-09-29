cmake_minimum_required(VERSION 3.16.3...3.19.7 FATAL_ERROR)

project(SlicePlaneOpacity)

# Extension metadata
set(EXTENSION_HOMEPAGE "https://github.com/youyouhdhd/SlicerSlicePlaneOpacity")
set(EXTENSION_CATEGORY "Visualization")
set(EXTENSION_CONTRIBUTORS "youyouhdhd")
set(EXTENSION_DESCRIPTION "Control the opacity and 3D visibility of the Red, Yellow, and Green slice planes in 3D Slicer.")
set(EXTENSION_ICONURL "https://raw.githubusercontent.com/youyouhdhd/SlicerSlicePlaneOpacity/main/SlicePlaneOpacity/Resources/Icons/SlicePlaneOpacity.png")
set(EXTENSION_SCREENSHOTURLS "https://raw.githubusercontent.com/youyouhdhd/SlicerSlicePlaneOpacity/main/Documentation/SlicePlaneOpacityOverview.png")
set(EXTENSION_DEPENDS "NA")

find_package(Slicer REQUIRED)
include(${Slicer_USE_FILE})

add_subdirectory(SlicePlaneOpacity)

include(${Slicer_EXTENSION_GENERATE_CONFIG})
include(${Slicer_EXTENSION_CPACK})
