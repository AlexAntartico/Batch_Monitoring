# Autosys Job Commands

`sendevent`: Used to control jobs (start, stop, force start, etc.) and the Autosys daemon itself

`autorep`:  Provides detailed information about jobs, boxes, machines, and global variables.

`autostatus`:  Reports the current status of a job or the value of an Autosys global variable.

`job_depends`: Displays job dependencies.

`autosyslog`: Displays Autosys log messages.

`jil`: Used to add, modify, or delete jobs and other Autosys objects from the command line.

Broadcom documentation [here.](https://techdocs.broadcom.com/us/en/ca-enterprise-software/intelligent-automation/autosys-workload-automation/12-1-01/monitoring-and-reporting/overview-and-key-features/manage-jobs-alerts/manage-job-events-in-monitoring/manage-job-events-in-monitorin-5.html)

| Category | Command | Description |
|---|---|---|
| **Job Control** | `sendevent -E STARTJOB -J job_name` | Starts a job |
|  | `sendevent -E FORCE_STARTJOB -J job_name` | Force starts a job, overriding dependencies |
|  | `sendevent -E KILLJOB -J job_name` | Kills a job |
|  | `sendevent -E JOB_ON_ICE -J job_name` | Deactivates job; doesn't impact dependent jobs |
|  | `sendevent -E JOB_OFF_ICE -J job_name` | Reactivates job; runs at next scheduled time |
|  | `sendevent -E JOB_ON_HOLD -J job_name` | Prevents the job from running; holds dependent jobs |
|  | `sendevent -E JOB_OFF_HOLD -J job_name` | Releases a job from hold; runs immediately if conditions are met |
|  | `sendevent -E CHG_JOB_PRIORITY -J job_name -p new_priority_value` | Changes job priority; higher priority gets resource preference. Job priority ranges from 0 to 99, 0 being the highest priority |
|  | `sendevent -E JOB_BEGIN -J job_name` | Manually forces a job to start (use with caution) |
|  | `sendevent -E JOB_END -J job_name` | Manually forces a job to end |
| **Job and Machine Information** | `autorep -J job_name` | Displays job details |
|  | `autorep -J job_name -q` | Displays the JIL for the job |
|  | `autorep -M machine_name` | Displays machine details |
|  | `autorep -G global_variable_name` | Displays the value of a global variable |
|  | `autostatus -J job_name` | Displays the status of a job |
| **System Status and Logs** | `autosyslog -J job_name` | Displays log messages for a specific job |
