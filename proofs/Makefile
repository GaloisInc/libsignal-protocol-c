LLVM_LINK ?= llvm-link
SAW ?= saw
BC = curve25519.bc

all: ${BC}

build/Makefile:
	mkdir build
	(cd build && CC=clang CXX=clang++ cmake -DCMAKE_BUILD_TYPE=Debug -DCMAKE_C_FLAGS=-save-temps ../..)

${BC}: build/Makefile
	make -C build
	${LLVM_LINK} -o ${BC} `find build/src/curve25519 -name "*.bc"`

verify: ${BC}
	${SAW} verify.saw

clean:
	rm -rf ${BC} build
