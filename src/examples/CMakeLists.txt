SET(TARGETS 
    convert
    subimage
    invert
    invert_explicitly
    resize
    smooth
    profile
    pyramid
    edge
    watershed
    weightedWatersheds
    voronoi
    total_variation)

ADD_CUSTOM_TARGET(examples)

FOREACH(TARGET ${TARGETS})
    ADD_EXECUTABLE(example_${TARGET} EXCLUDE_FROM_ALL ${TARGET}.cxx)
    ADD_DEPENDENCIES(examples example_${TARGET})
    TARGET_LINK_LIBRARIES(example_${TARGET} vigraimpex)
ENDFOREACH(TARGET)
