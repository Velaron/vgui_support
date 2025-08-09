cmake_minimum_required(VERSION 3.5)
project(vgui_support)

if(NOT XASH_SDK)
	set(XASH_SDK "../")
endif()

set(VGUI_SUPPORT_LIB vgui_support)

file(GLOB_RECURSE VGUI_SUPPORT_SRC "*.cpp")

include_directories(
	"${XASH_SDK}/common"
	"${XASH_SDK}/dlls"
	"${XASH_SDK}/public"
	"${XASH_SDK}/engine"
	"vgui-dev/include"
)

add_definitions(-DINTERNAL_VGUI_SUPPORT -DSTDINT_H="stdint.h")

add_library(${VGUI_SUPPORT_LIB} OBJECT ${VGUI_SUPPORT_SRC})