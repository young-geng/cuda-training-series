# Makefile for CUDA training exercises hw1

.PHONY: clean test_task1 test_task1_solution profile_task1 profile_task1_solution test_task2 test_task2_solution profile_task2 profile_task2_solution

task1: task1.cu
	nvcc -o task1 task1.cu

test_task1: task1
	./task1

task1_solution: task1_solution.cu
	nvcc -o task1_solution task1_solution.cu

test_task1_solution: task1_solution
	./task1_solution

task2: task2.cu
	nvcc -o task2 task2.cu

test_task2: task2
	./task2

profile_task2: task2
	ncu ./task2 | tee task2_profile.txt

task2_solution: task2_solution.cu
	nvcc -o task2_solution task2_solution.cu

test_task2_solution: task2_solution
	./task2_solution

profile_task2_solution: task2_solution
	ncu ./task2_solution | tee task2_solution_profile.txt

clean:
	@rm -f task1 task1_solution task1_profile.txt task1_solution_profile.txt task2 task2_solution task2_profile.txt task2_solution_profile.txt
