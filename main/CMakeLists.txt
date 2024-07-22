cmake_minimum_required(VERSION 3.16)

set(srcs
    "src/DHT_c.c"
    "src/DHT.cpp"
    "app_main.c")

set(includes
    "include"
    ".")

idf_component_register(SRCS ${srcs}
                    INCLUDE_DIRS ${includes})
