
# Release Planning Optimization

## About the Project

A university team project developed as part of the **CS454 – AI-Based Software Engineering** course at KAIST.

The project focuses on optimizing software release planning by assigning development tasks to programmers while considering multiple objectives:

- Maximizing business value delivered as early as possible
- Balancing workload across programmers
- Respecting task dependencies
- Meeting release schedules and capacity constraints

We implemented and compared three optimization algorithms to find effective task assignments.

## Algorithms

The project implements three approaches:

- **Greedy Algorithm** – Assigns tasks based on their priority, estimated cost, and expected completion time.
- **Hill Climbing** – Iteratively improves a solution by swapping tasks or moving them between programmers.
- **Genetic Algorithm** – Uses selection, crossover, and mutation to explore and optimize task assignments.

The algorithms are evaluated using a fitness function that considers task priorities, release schedules, workload balance, and dependency violations.

## Dataset

We used real issue data from the [Apache ZooKeeper](https://zookeeper.apache.org/) project, obtained from Apache Jira. The evaluation dataset contains approximately **1,000 issues** with recorded time estimates or tracking data.

## Results

We evaluated and compared the algorithms on the ZooKeeper dataset.

The Genetic Algorithm achieved the highest fitness score in our experiments, followed by Hill Climbing and the Greedy Algorithm. However, limitations in the available issue data made it difficult to compare the generated schedules directly with the project's real release plans.

## Getting Started

Run the application using:

```bash
python main.py
```

### Command-Line Options

| Option | Description | Default |
|--------|-------------|---------|
| `-a`, `--algorithm` | Algorithm: `greedy`, `hill_climbing`, `genetic` | `genetic` |
| `-t`, `--tasks_file` | Path to CSV file containing project issues | ZooKeeper dataset (1,000 issues) |
| `-p`, `--programmers_file` | Path to CSV file defining programmers and their efficiency | 4 sample programmers |
| `-r`, `--releases_file` | Path to CSV file defining release windows and capacities | 6 releases, each 10 days long |
