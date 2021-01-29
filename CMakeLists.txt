cmake_minimum_required(VERSION 3.10)
project(lua)

set(lua-src
  lapi.c
  lcode.c
  ldebug.c
  ldo.c
  ldump.c
  lfunc.c
  lgc.c
  llex.c
  lmem.c
  lobject.c
  lopcodes.c
  lparser.c
  lstate.c
  lstring.c
  ltable.c
  ltm.c
  lundump.c
  lvm.c
  lzio.c
  ltests.c
  lauxlib.c
  lbaselib.c
  ldblib.c
  liolib.c
  lmathlib.c
  loslib.c
  ltablib.c
  lstrlib.c
  loadlib.c
  linit.c
)
add_library(lua STATIC ${lua-src})
target_include_directories(lua PUBLIC .)
if (NOT MSVC)
  target_compile_definitions(lua PUBLIC LUA_USE_MKSTEMP)
endif()
