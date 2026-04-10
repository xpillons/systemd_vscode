# Open OnDemand Systemd VSCode application
Launch VSCode as a web server running as a systemd job.
Require VSCode version 1.97.0+ 

## CycleCloud Workspace Integration

This app uses `global_ccw_clusters` and `global_ccw_queues` form attributes, which are dynamically provided by [CycleCloud Workspace](https://learn.microsoft.com/azure/cyclecloud/) (CCW). These attributes do not need to be defined in `form.yml.erb`; they are automatically injected by the CCW framework at runtime:

- `global_ccw_clusters` — Populates the cluster selector dropdown, allowing users to choose which CycleCloud cluster to submit the job to. The value is passed to `submit.yml.erb` as the `cluster:` field.
- `global_ccw_queues` — Populates the partition/queue selector dropdown for the selected cluster. The value is passed as a `-p` scheduler argument in `submit.yml.erb`.
