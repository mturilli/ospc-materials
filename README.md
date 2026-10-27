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
