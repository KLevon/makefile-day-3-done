
# GOAL:
#    compile all .c files
#    link object files into static library
#    all files must be created in ../build directory
#
# HELP:
#    main target of this makefile is static library. That library is built last,
#    it depends on object files. Object files depend on source files and headers.
#    compile source file gcc cmd:
#        gcc -c [source_file] -I[headers_path] -o [object_name]
#    create archive gcc cmd:
#        ar -rvs [library_name] [list_object_files]
#

SRC_FILES := $(wildcard *.c)
_OBJ_FILES := $(SRC_FILES:.c=.o)
OBJ_FILES := $(addprefix $(BUILD_DIR)/,$(_OBJ_FILES)) 
HEADERS := $(widlcard *.h)

TARGET_LIB := $(BUILD_DIR)/libutils.a

$(BUILD_DIR)/%.a: $(OBJ_FILES)
	ar -rvs $@ $^

$(BUILD_DIR)/%.o: %.c $(HEADERS)
	gcc -c $< -I. -o $@

.PRECIOUS: $(OBJ_FILES)

$(TARGET_LIB):


