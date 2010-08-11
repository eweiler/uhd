#
# Copyright 2010 Ettus Research LLC
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.
#

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
PROJECT(UHD-images NONE)

########################################################################
# Config Files (include order is important)
########################################################################
INCLUDE(${CMAKE_SOURCE_DIR}/../host/config/Python.cmake)
INCLUDE(${CMAKE_SOURCE_DIR}/../host/config/Version.cmake)

########################################################################
# Setup CPack
########################################################################
SET(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Ettus Research - Universal Hardware Driver Images")
SET(CPACK_PACKAGE_VENDOR              "Ettus Research LLC")
SET(CPACK_PACKAGE_CONTACT             "support@ettus.com")
SET(CPACK_PACKAGE_VERSION_MAJOR ${UHD_VERSION_MAJOR})
SET(CPACK_PACKAGE_VERSION_MINOR ${UHD_VERSION_MINOR})
SET(CPACK_PACKAGE_VERSION_PATCH ${UHD_VERSION_PATCH})
INCLUDE(CPack) #include after setting vars
MESSAGE(STATUS "Version: ${CPACK_PACKAGE_VERSION}")

########################################################################
# Install Images
########################################################################
INSTALL(DIRECTORY ${CMAKE_SOURCE_DIR}/images DESTINATION share/uhd)