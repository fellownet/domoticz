cmake_minimum_required(VERSION 2.6)

project (HOMEKIT C)

SET(HOMEKIT_INCLUDE_DIRS "${CMAKE_CURRENT_SOURCE_DIR}")
SET(HOMEKIT_LIBRARIES homekit)

SET(LIBRARY_OUTPUT_PATH "" CACHE INTERNAL 
  "Where to put the libraries for HOMEKIT"
  )

SET(
homekit_SRCS
tlv8/tlv8.cpp
srp/cstr.c
srp/srp.c
srp/srp6_server.c
srp/t_math.c
srp/t_misc.c
srp/t_read.c
srp/t_truerand.c
hkdf/hkdf.c
chacha20/chacha20_simple.c
poly1305/poly1305.c
ed25519/ed25519-donna.c
ed25519/ed25519.c
curve25519/curve25519-donna.c
)
ADD_LIBRARY(homekit STATIC ${homekit_SRCS})
