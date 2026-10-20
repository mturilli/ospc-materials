# OSPC course materials

Material for the Operating Systems and Parallel Computing course: the interactive animations used in class and, over time, some of the code behind the course.

## Animations

- [Three policies, step by step](https://mturilli.github.io/ospc-materials/animations/scheduling-policies.html): FIFO, SJF and round robin run the same three jobs. See when each job first runs and when it finishes, and compare the averages.
- [MLFQ, step by step](https://mturilli.github.io/ospc-materials/animations/mlfq.html): a multi-level feedback queue with a long, a short and an interactive job. See which queue each job ends up in, then why the scheduler needs a priority boost.
- [Three Linux schedulers, step by step](https://mturilli.github.io/ospc-materials/animations/linux-schedulers.html): O(1), CFS and EEVDF run the same three jobs. Step through them one event at a time and compare turnaround and response.
- [Queues and cores, step by step](https://mturilli.github.io/ospc-materials/animations/multicore-queues.html): one shared queue on four cores, then one queue per core. See how jobs move between cores, the load imbalance when a job finishes, and how work stealing fixes it.

Each animation is a single HTML file with no dependencies. Open the link, or download the file and open it in a browser. It also works offline.
