# slurmee

Simple Python 3 package to get information when running Python programs in [slurm](https://slurm.schedmd.com/documentation.html). 

## Usage

```python
import slurmee

print(f"Slurm job id: {slurmee.get_job_id()}")
print(f"Slurm job name: {slurmee.get_job_name()}")
print(f"Slurm submit dir: {slurmee.get_submit_dir()}")
print(f"Slurm job nodelist: {slurmee.get_job_nodelist()}")
print(f"Slurm submit host: {slurmee.get_submit_host()}")
print(f"Slurm job num_nodes: {slurmee.get_job_num_nodes()}")
print(f"Slurm cpus on node: {slurmee.get_cpus_on_node()}")
print(f"Slurm ntasks: {slurmee.get_ntasks()}")
print(f"Slurm nodeid: {slurmee.get_nodeid()}")
```

Methods return `None` if not running inside of slurm. This can be used to check e.g. 

```python
if slurmee.get_job_id():
    print("Running inside of slurm!")
```

## Development

This package has no external dependencies. The tests can be run via 

    python3 -m unittest