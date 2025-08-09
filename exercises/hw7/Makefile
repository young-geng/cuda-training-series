# Makefile for CUDA training exercises hw1

.PHONY: clean all test_overlap test_overlap_solution test_multi test_multi_solution

all: hello hello_solution vector_add vector_add_solution matrix_mul matrix_mul_solution

overlap: overlap.cu
	nvcc -o overlap overlap.cu -DUSE_STREAMS

test_overlap: overlap
	./overlap

profile_overlap: overlap
	nsys profile -o overlap.qdrep overlap

overlap_solution: overlap_solution.cu
	nvcc -o overlap_solution overlap_solution.cu -DUSE_STREAMS

test_overlap_solution: overlap_solution
	./overlap_solution

multi: multi.cu
	nvcc -o multi multi.cu

test_multi: multi
	./multi

multi_solution: multi_solution.cu
	nvcc -o multi_solution multi_solution.cu

test_multi_solution: multi_solution
	./multi_solution

clean:
	@rm -f overlap overlap_solution multi multi_solution overlap.nsys-rep