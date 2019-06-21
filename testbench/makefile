DEBUG = NONE

DFLAGS = -relocation-model=pic -w -O3 -lowmem -release -boundscheck=off

all: axi4_sha3.vvp axi4_sha3.vpi

clean:
	rm -f axi4_sha3.vvp axi4_sha3.vpi axi4_sha3.o axi4_sha3.vcd
	cd tiny_sha3; make clean

run: axi4_sha3.vvp axi4_sha3.vpi
	vvp -M. -maxi4_sha3 axi4_sha3.vvp +UVM_TESTNAME=axi4_sha3.random_test # +UVM_OBJECTION_TRACE # +UVM_VERBOSITY=DEBUG

axi4_sha3.vvp: axi4_sha3.v ../rtl/*.v
	iverilog -o $@ $^

axi4_sha3.vpi: axi4_sha3.d tiny_sha3/libsha3.a
	ldc2 $(DFLAGS) -shared -of$@ -L-luvm-ldc-shared -L-lesdl-ldc-shared \
		-L-lphobos2-ldc-shared -L-ldl $^

tiny_sha3/libsha3.a:
	cd tiny_sha3; make lib
