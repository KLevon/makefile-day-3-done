
# GOAL:
#    compile main.c file
#    link object file with previously made static libraries into an executable
#    all files must be created in ../build directory
#
# HELP:
#    main target of this makefile is final executable. It depends on object files
#    and static libraries.
#    compile source file gcc cmd:
#        gcc -c [source_file] -I[headers_path] -o [object_name]
#    link libraries and object files
#        gcc [object_files] [path to libraries with prefix -L] [library names with prefix -l] -o main.exe
#

SRC_FILES := $(wildcard *.c)
_OBJ_FILES := $(SRC_FILES:.c=.o)
OBJ_FILES := $(addprefix $(BUILD_DIR)/,$(_OBJ_FILES))

_LIBRARIES := libutils.a libprinter.a libnothing.a
LIBRARIES := $(addprefix $(BUILD_DIR)/,$(LIBRARIES))
LIB_LINK := -lutils -lprinter -lnothing

HEADER_PATHS := ../1_utils ../2_printer/include ../3_nothing/include
HEADER_LINK := $(addprefix -I,$(HEADER_PATHS))

TARGET_EXE := $(BUILD_DIR)/main.exe

$(BUILD_DIR)/%.exe: $(OBJ_FILES) $(LIBRARIES)
	gcc $(OBJ_FILES) -L$(BUILD_DIR) $(LIB_LINK) -o $@

$(BUILD_DIR)/%.o: %.c
	gcc -c $< $(HEADER_LINK) -o $@

#.PRECIOUS: $(OBJ_FILES)

$(TARGET_EXE):
