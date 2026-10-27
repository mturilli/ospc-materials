# OSPC course materials

Material for the Operating Systems and Parallel Computing course: the interactive animations used in class and, over time, some of the code behind the course.

## Animations

- [Three policies, step by step](https://mturilli.github.io/ospc-materials/animations/scheduling-policies.html): FIFO, SJF and round robin run the same three jobs. See when each job first runs and when it finishes, and compare the averages.
- [MLFQ, step by step](https://mturilli.github.io/ospc-materials/animations/mlfq.html): a multi-level feedback queue with a long, a short and an interactive job. See which queue each job ends up in, then why the scheduler needs a priority boost.
- [Three Linux schedulers, step by step](https://mturilli.github.io/ospc-materials/animations/linux-schedulers.html): O(1), CFS and EEVDF run the same three jobs. Step through them one event at a time and compare turnaround and response.
- [Queues and cores, step by step](https://mturilli.github.io/ospc-materials/animations/multicore-queues.html): one shared queue on four cores, then one queue per core. See how jobs move between cores, the load imbalance when a job finishes, and how work stealing fixes it.
- [When does the GPU pay off?](https://mturilli.github.io/ospc-materials/animations/gpu-offload.html): copy the data to the GPU, compute, copy the result back, and compare with the same work on the CPU, measured on our cluster. See from what size a matrix product pays off, why adding two arrays does not, and what changes when the data stays on the GPU.
- [Compute or move?](https://mturilli.github.io/ospc-materials/animations/compute-or-move.html): operations per second against operations per byte, measured on our cluster. See why `a @ a` runs 200 times faster than `a + b` on the same CPUs, and where the GPU's limits sit, with and without the copies.
- [Waiting in the Slurm queue](https://mturilli.github.io/ospc-materials/animations/slurm-queue.html): jobs arrive, wait and start on a small partition. See why a job that asks for the CPUs it uses, with an honest time limit, starts sooner and lets other jobs start sooner too.

Each animation is a single HTML file with no dependencies. Open the link, or download the file and open it in a browser. It also works offline.

## Lab 1: The Nightly Report

What went wrong in the three tasks we did together in class, step by step. At each step, predict what happens, then watch.

- [Task 1: Where the Memory Went](https://mturilli.github.io/ospc-materials/lab1/where-the-memory-went.html): a replay of `report.py` on the whole file. See how the memory grows from reading the file to the monthly tables, why the kernel kills the process instead of Python raising an error, and where the missing line of the log went.
- [Task 2: Where grep Looked](https://mturilli.github.io/ospc-materials/lab1/where-grep-looked.html): `extracts.sh` one line at a time. See which file the relative path names after `cd`, where the error message of `grep` goes, and why the script still prints `done` and exits with status 0.
- [Task 3: Three System Calls per Order](https://mturilli.github.io/ospc-materials/lab1/three-system-calls-per-order.html): what `audit.py` asks the kernel to do for every order, and what it costs on 8.4 million orders. See where each line is when `close` returns, and how many `write` calls one open file needs.

Like the animations, each page is a single HTML file with no dependencies, and it works offline.
