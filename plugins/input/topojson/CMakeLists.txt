project(input-topojson)

add_library(input-topojson MODULE
    topojson_datasource.cpp
    topojson_featureset.cpp
)
add_library(mapnik::plugin::input::topojson ALIAS input-topojson)
target_link_libraries(input-topojson PRIVATE
    mapnik::mapnik
    mapnik::json
)
set_target_properties(input-topojson PROPERTIES 
    OUTPUT_NAME "topojson"
    PREFIX "${_plugin_prefix}"
    SUFFIX "${_plugin_suffix}"
)

mapnik_install_plugin(input-topojson)
