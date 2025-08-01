# Makefile for CUDA training exercises hw1

.PHONY: clean all test_hello test_hello_solution test_vector_add test_vector_add_solution test_matrix_mul test_matrix_mul_solution

all: hello hello_solution vector_add vector_add_solution matrix_mul matrix_mul_solution

hello: hello.cu
	nvcc -o hello hello.cu

test_hello: hello
	./hello

hello_solution: hello_solution.cu
	nvcc -o hello_solution hello_solution.cu

test_hello_solution: hello_solution
	./hello_solution

vector_add: vector_add.cu
	nvcc -o vector_add vector_add.cu

test_vector_add: vector_add
	./vector_add

vector_add_solution: vector_add_solution.cu
	nvcc -o vector_add_solution vector_add_solution.cu

test_vector_add_solution: vector_add_solution
	./vector_add_solution

matrix_mul: matrix_mul.cu
	nvcc -o matrix_mul matrix_mul.cu

test_matrix_mul: matrix_mul
	./matrix_mul

matrix_mul_solution: matrix_mul_solution.cu
	nvcc -o matrix_mul_solution matrix_mul_solution.cu

test_matrix_mul_solution: matrix_mul_solution
	./matrix_mul_solution

clean:
	@rm -f hello hello_solution vector_add vector_add_solution matrix_mul matrix_mul_solution