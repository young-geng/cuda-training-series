# Makefile for CUDA training exercises hw1

.PHONY: clean all test_matrix_sums test_matrix_sums_solution

all: matrix_sums matrix_sums_solution

matrix_sums: matrix_sums.cu
	nvcc -o matrix_sums matrix_sums.cu

test_matrix_sums: matrix_sums
	./matrix_sums

profile_matrix_sums: matrix_sums
	ncu ./matrix_sums | tee matrix_sums_profile.txt

matrix_sums_solution: matrix_sums_solution.cu
	nvcc -o matrix_sums_solution matrix_sums_solution.cu

test_matrix_sums_solution: matrix_sums_solution
	./matrix_sums_solution

clean:
	@rm -f matrix_sums matrix_sums_solution