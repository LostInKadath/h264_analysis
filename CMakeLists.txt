cmake_minimum_required(VERSION 3.16)

set(CMAKE_POLICY_CMP0048 NEW)		# For project(VERSION)
set(CMAKE_MFC_FLAG 1)				# For static MFC

project(SpecialVH264
	VERSION 1.0.0.0
	HOMEPAGE_URL https://github.com/LostInKadath/h264_analysis
	LANGUAGES CXX C
)

set(SOURCES
	bs.h
	h264_analyze.cpp
	h264_analyze.h
	h264_avcc.cpp
	h264_avcc.h
	h264_sei.cpp
	h264_sei.h
	h264_stream.cpp
	h264_stream.h
	NALParse.cpp
	NALParse.h
	resource.h
	SpecialVH264.cpp
	SpecialVH264.h
	SpecialVH264Dlg.cpp
	SpecialVH264Dlg.h
	stdafx.h
)

set(RESOURCES
	ReadMe.txt
	SpecialVH264.rc
	res/264.ico
	res/264_ico.png
	res/main_theme_h264.bmp
	res/main_theme_h264_en.bmp
	res/SpecialVH264.ico
	res/SpecialVH264.rc2
)

source_group(cmake REGULAR_EXPRESSION "(cmake_pch\\.hxx|cmake_pch\\.cxx|CMakeLists.txt)")
source_group(src FILES ${SOURCES})
source_group(res FILES ${RESOURCES})

add_executable(SpecialVH264 WIN32 ${SOURCES} ${RESOURCES})

target_precompile_headers(SpecialVH264 PRIVATE stdafx.h)
target_compile_definitions(SpecialVH264 PRIVATE -D_AFXDLL)




