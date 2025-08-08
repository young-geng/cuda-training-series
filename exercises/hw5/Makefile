# Makefile for CUDA training exercises hw1

.PHONY: clean all test_matrix_sums test_matrix_sums_solution

all: matrix_sums matrix_sums_solution

reductions: reductions.cu
	nvcc -o reductions reductions.cu

test_reductions: reductions
	./reductions

profile_reductions: reductions
	ncu ./reductions | tee reductions_profile.txt

max_reduction: max_reduction.cu
	nvcc -o max_reduction max_reduction.cu

test_max_reduction: max_reduction
	./max_reduction

max_reduction_solution: max_reduction_solution.cu
	nvcc -o max_reduction_solution max_reduction_solution.cu

test_max_reduction_solution: max_reduction_solution
	./max_reduction_solution

matrix_sums: matrix_sums.cu
	nvcc -o matrix_sums matrix_sums.cu

test_matrix_sums: matrix_sums
	./matrix_sums

profile_matrix_sums: matrix_sums
	ncu ./matrix_sums | tee matrix_sums_profile.txt
	ncu --metrics l1tex__t_sectors_pipe_lsu_mem_global_op_ld.sum,l1tex__t_requests_pipe_lsu_mem_global_op_ld.sum \
		./matrix_sums | tee -a matrix_sums_profile.txt

matrix_sums_solution: matrix_sums_solution.cu
	nvcc -o matrix_sums_solution matrix_sums_solution.cu

test_matrix_sums_solution: matrix_sums_solution
	./matrix_sums_solution

profile_matrix_sums_solution: matrix_sums_solution
	ncu ./matrix_sums_solution | tee matrix_sums_solution_profile.txt
	ncu --metrics l1tex__t_sectors_pipe_lsu_mem_global_op_ld.sum,l1tex__t_requests_pipe_lsu_mem_global_op_ld.sum \
		./matrix_sums_solution | tee -a matrix_sums_solution_profile.txt

clean:
	@rm -f reductions reductions_profile.txt \
		max_reduction max_reduction_solution \
		matrix_sums matrix_sums_solution \
		matrix_sums_profile.txt \
		max_reduction_profile.txt