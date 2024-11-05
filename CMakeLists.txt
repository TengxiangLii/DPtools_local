
# install the dptools only on your machine/directory
# author: Tengxiang Li
# date:   05/11/2024

cmake_minimum_required(VERSION 3.29)
project(dptools)

# specify the path to python interpreter
set(PYTHON_INTERPRETER "/home/elliot/miniconda3/envs/dptools/bin/python3.12")

# set the installation prefix
set(CMAKE_INSTALL_PREFIX "/home/elliot/opt/dptools")

# if you want to install the executable files under the directory of the source code
# set(prefix ${CMAKE_BINARY_DIR}/${CMAKE_INSTALL_PREFIX})
set(prefix ${CMAKE_INSTALL_PREFIX})
set(cmake-command "
  execute_process(
    COMMAND ${PYTHON_INTERPRETER} -m pip install --no-deps --prefix ${prefix} .
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
")

install(CODE "${cmake-command}")
