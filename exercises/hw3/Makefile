# Makefile for CUDA training exercises hw1

.PHONY: clean all test_vector_add test_vector_add_solution test_matrix_mul test_matrix_mul_solution

all: vector_add vector_add_solution matrix_mul matrix_mul_solution

vector_add: vector_add.cu
	nvcc -o vector_add vector_add.cu

test_vector_add: vector_add
	./vector_add

vector_add_solution: vector_add_solution.cu
	nvcc -o vector_add_solution vector_add_solution.cu

test_vector_add_solution: vector_add_solution
	./vector_add_solution

clean:
	@rm -f vector_add vector_add_solution