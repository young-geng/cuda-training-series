# Makefile for CUDA training exercises hw1

.PHONY: clean all test_stencil_1d test_stencil_1d_solution test_matrix_mul_shared test_matrix_mul_shared_solution

all: stencil_1d stencil_1d_solution matrix_mul_shared matrix_mul_shared_solution

stencil_1d: stencil_1d.cu
	nvcc -o stencil_1d stencil_1d.cu

test_stencil_1d: stencil_1d
	./stencil_1d

stencil_1d_solution: stencil_1d_solution.cu
	nvcc -o stencil_1d_solution stencil_1d_solution.cu

test_stencil_1d_solution: stencil_1d_solution
	./stencil_1d_solution

matrix_mul_shared: matrix_mul_shared.cu
	nvcc -o matrix_mul_shared matrix_mul_shared.cu

test_matrix_mul_shared: matrix_mul_shared
	./matrix_mul_shared

matrix_mul_shared_solution: matrix_mul_shared_solution.cu
	nvcc -o matrix_mul_shared_solution matrix_mul_shared_solution.cu

test_matrix_mul_shared_solution: matrix_mul_shared_solution
	./matrix_mul_shared_solution

clean:
	@rm -f stencil_1d stencil_1d_solution matrix_mul_shared matrix_mul_shared_solution