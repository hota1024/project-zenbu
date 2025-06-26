PROJECT = core
FILELIST = $(PROJECT).f

TOP_MODULE = top
TB_PROGRAM = src/tb_verilator.cpp
OBJ_DIR = obj_dir/
SIM_NAME = sim
VERILATOR_FLAGS = ""
CXX = /opt/homebrew/Cellar/llvm/20.1.7/bin/clang

VERYL_VERSION = 0.14.0
VERYL = veryl +$(VERYL_VERSION)

clean:
	$(VERYL) clean
	rm -rf $(OBJ_DIR)
fmt:
	$(VERYL) fmt
build:
	$(VERYL) fmt
	$(VERYL) build
sim:
	CXX=$(CXX) verilator --cc $(VERILATOR_FLAGS) -f $(FILELIST) --exe $(TB_PROGRAM) --top-module $(PROJECT)_$(TOP_MODULE) --Mdir $(OBJ_DIR)
	make CXX=$(CXX) -C $(OBJ_DIR) -f V$(PROJECT)_$(TOP_MODULE).mk
	mv $(OBJ_DIR)/V$(PROJECT)_$(TOP_MODULE) $(OBJ_DIR)/$(SIM_NAME)

.PHONY: build clean sim
