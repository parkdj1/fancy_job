# Daily Number Incrementer

## Setup

1. Clone this repository:

```bash
git clone https://github.com/Shogun89/fancy_job
cd fancy_job
```

2.  Run the script

The script can be run without dependencies besides the Python standard library,
simply by running

```bash
python update_number.py
```

You might want to run the script manually for the first time to verify it works
before setting up a cronjob


```bash
# Use LLM
FANCY_JOB_USE_LLM=true uv run python update_number.py
```

3. Setup a cron job to run the script daily:

```bash
crontab -e
```

Add the following line to the crontab file:

```bash
0 6 * * * cd /path/to/your/repo && python update_number.py
# or with LLM
0 6 * * * cd /path/to/your/repo && FANCY_JOB_USE_LLM=true uv run python update_number.py
```

This will initially run the script at 6am the next day.

