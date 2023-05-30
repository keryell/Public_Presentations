world: 2023-05-30-NERSC-SYCL-tutorial-introduction.pdf
#	code/sycl_matrix_addition

# We have an index to compute
#MAKEINDEX=1

# Use pdfLaTeX instead of the legacy DVI LaTeX
USE_PDFTEX=1
#USE_PDFTEX=0

include ../../Makefiles/beamer.mk

# To compile the modern C++ programs
DPCPP_HOME=$$HOME/Xilinx/Projects/LLVM/worktrees/xilinx
#DPCPP_HOME=$$HOME/Xilinx/Projects/LLVM/worktrees/intel
CXX=$(DPCPP_HOME)/llvm/build/bin/clang++
CXXFLAGS = -fsycl -O2 -std=c++2b
#CXXFLAGS = -fsycl -fsycl-targets=nvptx64-nvidia-cuda \
#	-Xsycl-target-backend=nvptx64-nvidia-cuda \
#	--offload-arch=sm_61 -O2 -std=c++2b
#LDLIBS += -lboost_system -lboost_filesystem -lpthread
export LD_LIBRARY_PATH=$(DPCPP_HOME)/llvm/build/lib

%-run: %
	LD_LIBRARY_PATH=$(DPCPP_HOME)/llvm/build/lib \
	echo #$(DPCPP_HOME)/llvm/build/bin/sycl-ls
	LD_LIBRARY_PATH=$(DPCPP_HOME)/llvm/build/lib $<
