# Makefile for CUDA training exercises hw1

.PHONY: clean test_task1 test_task1_solution profile_task1 profile_task1_solution

task1: task1.cu
	nvcc -O3 -o task1 task1.cu

test_task1: task1
	./task1

profile_task1: task1
	ncu \
		--metrics l1tex__t_sectors_pipe_lsu_mem_global_op_ld.sum,l1tex__t_requests_pipe_lsu_mem_global_op_ld.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_ld.ratio,l1tex__t_sectors_pipe_lsu_mem_global_op_st.sum,l1tex__t_requests_pipe_lsu_mem_global_op_st.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_st.ratio,smsp__sass_average_data_bytes_per_sector_mem_global_op_ld.pct,smsp__sass_average_data_bytes_per_sector_mem_global_op_st.pct \
		./task1 \
	| tee task1_profile.txt

task1_solution: task1_solution.cu
	nvcc -O3 -o task1_solution task1_solution.cu

test_task1_solution: task1_solution
	./task1_solution

profile_task1_solution: task1_solution
	ncu \
		--metrics l1tex__t_sectors_pipe_lsu_mem_global_op_ld.sum,l1tex__t_requests_pipe_lsu_mem_global_op_ld.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_ld.ratio,l1tex__t_sectors_pipe_lsu_mem_global_op_st.sum,l1tex__t_requests_pipe_lsu_mem_global_op_st.sum,l1tex__average_t_sectors_per_request_pipe_lsu_mem_global_op_st.ratio,smsp__sass_average_data_bytes_per_sector_mem_global_op_ld.pct,smsp__sass_average_data_bytes_per_sector_mem_global_op_st.pct \
		./task1_solution \
	| tee task1_solution_profile.txt

clean:
	@rm -f task1 task1_solution task1_profile.txt task1_solution_profile.txt