project(input-shape)

add_library(input-shape MODULE 
    dbfile.cpp 
    dbf_test.cpp
    shape_datasource.cpp
    shape_featureset.cpp
    shape_index_featureset.cpp
    shape_io.cpp shape_utils.cpp
)
target_link_libraries(input-shape PRIVATE mapnik::mapnik)
set_target_properties(input-shape PROPERTIES 
    OUTPUT_NAME "shape"
    PREFIX "${_plugin_prefix}"
    SUFFIX "${_plugin_suffix}"
)

mapnik_install_plugin(input-shape)
