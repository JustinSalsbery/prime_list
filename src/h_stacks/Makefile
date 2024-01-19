
# Makefile: For stack implementations.
# author: Justin Salsbery

# User settings
SRCDIR := .
FILES := $(shell find $(SRCDIR) -name "*.c")
OUT := _main.out

# Compiler settings ; Windows not supported
OS := $(shell uname)

ifeq ($(OS),Linux)
CMP := gcc
endif

ifeq ($(OS),Darwin)
CMP := /opt/homebrew/opt/llvm/bin/clang
endif

BLDFLAGS := -DNDEBUG -flto -O3
TSTFLAGS := -Werror -Wall -Wextra -Wpedantic -Wshadow -Wconversion -Wfloat-equal \
	     -Wpointer-arith -Wdouble-promotion -Winit-self -Wnull-dereference \
	     -Wbad-function-cast -Wundef -Wmissing-prototypes -Wstrict-prototypes \
	     -Wformat-security -Wswitch-default -Wswitch-bool -Wswitch-enum \
	     -Wimplicit-fallthrough -Wmisleading-indentation -Wdangling-else \
	     -Wunreachable-code -Winline -Wcast-qual -Wnested-externs \
	     -Wlogical-not-parentheses -Wredundant-decls -Wtautological-compare \
	     -Wint-in-bool-context -fno-common -g -O0

# Useful options: { address, thread, leak, undefined }
ifdef DEBUG
TSTFLAGS += -fsanitize=${DEBUG}
endif

# Make settings
SHELL := bash

ifndef VERBOSE
.SILENT:
endif

.PHONY: help options
help options:
	echo "HI"
