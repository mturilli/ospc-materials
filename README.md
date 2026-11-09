# OSPC course materials

Material for the Operating Systems and Parallel Computing course: the interactive animations used in class and, over time, some of the code behind the course.

## Animations

- [Three policies, step by step](https://mturilli.github.io/ospc-materials/animations/scheduling-policies.html): FIFO, SJF and round robin run the same three jobs. See when each job first runs and when it finishes, and compare the averages.
- [MLFQ, step by step](https://mturilli.github.io/ospc-materials/animations/mlfq.html): a multi-level feedback queue with a long, a short and an interactive job. See which queue each job ends up in, then why the scheduler needs a priority boost.
- [Three Linux schedulers, step by step](https://mturilli.github.io/ospc-materials/animations/linux-schedulers.html): O(1), CFS and EEVDF run the same three jobs. Step through them one event at a time and compare turnaround and response.
- [Queues and cores, step by step](https://mturilli.github.io/ospc-materials/animations/multicore-queues.html): one shared queue on four cores, then one queue per core. See how jobs move between cores, the load imbalance when a job finishes, and how work stealing fixes it.
- [Vectorized operations, step by step](https://mturilli.github.io/ospc-materials/animations/vectorization.html): the same additions as a Python loop, as a compiled loop, and with SIMD instructions that handle 4 or 8 numbers at once, measured on our cluster. See why NumPy is fast, when SIMD pays off, and why data from RAM slows every version down.
- [When does the GPU pay off?](https://mturilli.github.io/ospc-materials/animations/gpu-offload.html): copy the data to the GPU, compute, copy the result back, and compare with the same work on the CPU, measured on our cluster. See from what size a matrix product pays off, why adding two arrays does not, and what changes when the data stays on the GPU.
- [Compute or move?](https://mturilli.github.io/ospc-materials/animations/compute-or-move.html): operations per second against operations per byte, measured on our cluster. See why `a @ a` runs 200 times faster than `a + b` on the same CPUs, and where the GPU's limits sit, with and without the copies.
- [Waiting in the Slurm queue](https://mturilli.github.io/ospc-materials/animations/slurm-queue.html): jobs arrive, wait and start on a small partition. See why a job that asks for the CPUs it uses, with an honest time limit, starts sooner and lets other jobs start sooner too.
- [Threads in Python, step by step](https://mturilli.github.io/ospc-materials/animations/python-threads.html): four threads in one process, with one GIL. See why threads help when a program waits and not when it computes, and how a wait between read and write loses an update.
- [A pool of processes, step by step](https://mturilli.github.io/ospc-materials/animations/python-processes.html): workers with their own memory and their own GIL, on the cores of a job, measured on our cluster. See what a pool does with data and compute tasks, what big arrays and tiny tasks cost, why 4 CPUs are 2 cores, and where Linux puts the workers.
- [How much faster? Scaling, step by step](https://mturilli.github.io/ospc-materials/animations/scaling.html): one program with 1 to 32 workers, measured on our cluster. See how far the speedup goes, why Amdahl's law stops it, what happens when every worker reads from the same memory, and what weak scaling measures.
- [Threads inside the libraries, step by step](https://mturilli.github.io/ospc-materials/animations/library-threads.html): one matrix product split among threads, then a pool of workers that each start threads of their own, measured on our cluster. See why 4 workers with 4 threads each on 4 CPUs run several times slower, and why small products suffer most.
- [What Ctrl-C reaches, step by step](https://mturilli.github.io/ospc-materials/animations/what-ctrl-c-reaches.html): Ctrl-C, `kill -INT` and the fix of `stats.sh` from Lab 1. See which processes receive the signal, why the workers kept running with PPID 1, and how two traps stop them.
- [Where the bytes wait, step by step](https://mturilli.github.io/ospc-materials/animations/where-the-bytes-wait.html): a line of output on its way from `print` to the disk. See what SIGTERM and SIGKILL do to a line still in Python's buffer, what `close()` guarantees and what only `os.fsync` adds, and how many `write` calls one open file needs.
- [Reading a profile, step by step](https://mturilli.github.io/ospc-materials/animations/reading-a-profile.html): where the times of a cProfile listing come from. See which function is running at each moment, why `tottime` and `cumtime` differ, and why `<module>` always has the largest `cumtime`.

Each animation is a single HTML file with no dependencies. Open the link, or download the file and open it in a browser. It also works offline.

## Notebooks

Notebooks we run in class on the cluster, in the kernel OSPC (Python 3.12). In JupyterLab, open a terminal (File > New > Terminal) and download the notebook with `curl -O` followed by its link.

- [Threads and processes in Python](https://mturilli.github.io/ospc-materials/notebooks/threads-processes.ipynb): start threads and processes by hand, see what they share, compare them in batch jobs with `sbatch`, then lose updates in a race and fix it with a lock.
- [How much faster?](https://mturilli.github.io/ospc-materials/notebooks/scaling.ipynb): run one program with 1 to 32 workers in a batch job, compute speedup and efficiency, compare them with Amdahl's law, and see what changes when the tasks read from memory and when the problem grows with the workers.
- [Threads inside the libraries](https://mturilli.github.io/ospc-materials/notebooks/library-threads.ipynb): find out which NumPy calls use threads, see and set the threads of NumPy and scikit-learn, and measure what happens when a pool of processes meets a library that starts threads in every worker.

## Lab 1: The Nightly Report

What went wrong in the warm-up and in the three tasks we did together in class, step by step. At each step, predict what happens, then watch.

- [Warm-up: Permission Denied](https://mturilli.github.io/ospc-materials/lab1/permission-denied.html): why `./run_report.sh` was refused. See what the ten characters of `ls -l` say, why `bash run_report.sh` works anyway, and what `chmod +x` changes in the file and in git.
- [Task 1: Where the Memory Went](https://mturilli.github.io/ospc-materials/lab1/where-the-memory-went.html): a replay of `report.py` on the whole file. See how the memory grows from reading the file to the monthly tables, why the kernel kills the process instead of Python raising an error, how the peak grows on 1, 2 and 4 million orders, and where the missing line of the log went.
- [Task 2: Where grep Looked](https://mturilli.github.io/ospc-materials/lab1/where-grep-looked.html): `extracts.sh` one line at a time. See which file the relative path names after `cd`, where the error message of `grep` goes, and why the script still prints `done` and exits with status 0.
- [Task 3: Three System Calls per Order](https://mturilli.github.io/ospc-materials/lab1/three-system-calls-per-order.html): what `audit.py` asks the kernel to do for every order, and what it costs on 8.4 million orders. See where each line is when `close` returns, and how many `write` calls one open file needs.

Like the animations, each page is a single HTML file with no dependencies, and it works offline.
