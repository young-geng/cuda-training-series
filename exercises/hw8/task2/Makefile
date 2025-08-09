# Makefile for CUDA training exercises hw1

.PHONY: clean test_task2 test_task2_solution profile_task2 profile_task2_solution profile_all

task2: task2.cu
	nvcc -O3 -o task2 task2.cu

test_task2: task2
	./task2

profile_task2: task2
	ncu \
		--metrics l1tex__t_sectors_pipe_lsu_mem_global_op_ld.sum,l1tex__t_requests_pipe_lsu_mem_global_op_ld.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_ld.ratio,l1tex__t_sectors_pipe_lsu_mem_global_op_st.sum,l1tex__t_requests_pipe_lsu_mem_global_op_st.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_st.ratio,smsp__sass_average_data_bytes_per_sector_mem_global_op_ld.pct,smsp__sass_average_data_bytes_per_sector_mem_global_op_st.pct \
		./task2 \
	| tee task2_profile.txt

task2_solution: task2_solution.cu
	nvcc -O3 -o task2_solution task2_solution.cu

test_task2_solution: task2_solution
	./task2_solution

profile_task2_solution: task2_solution
	ncu \
		--metrics l1tex__t_sectors_pipe_lsu_mem_global_op_ld.sum,l1tex__t_requests_pipe_lsu_mem_global_op_ld.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_ld.ratio,l1tex__t_sectors_pipe_lsu_mem_global_op_st.sum,l1tex__t_requests_pipe_lsu_mem_global_op_st.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_st.ratio,smsp__sass_average_data_bytes_per_sector_mem_global_op_ld.pct,smsp__sass_average_data_bytes_per_sector_mem_global_op_st.pct \
		./task2_solution \
	| tee task2_solution_profile.txt

profile_all: profile_task2 profile_task2_solution

clean:
	@rm -f task2 task2_solution task2_profile.txt task2_solution_profile.txt