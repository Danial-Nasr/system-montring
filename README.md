# system-montring


# System Resource Monitor

This Bash script monitors system resources, including disk usage, CPU usage, memory usage, and the top 5 memory-consuming processes. It generates logs, displays resource statistics in the terminal, and sends email alerts when specified thresholds are exceeded.

---

## Features

- **Disk Usage Monitoring**  
  Reports disk usage for all partitions and triggers an alert if usage exceeds the specified threshold.

- **CPU Usage Monitoring**  
  Monitors CPU usage and sends an alert if it surpasses the threshold.

- **Memory Usage Monitoring**  
  Displays total, used, and free memory.

- **Top Memory-Consuming Processes**  
  Lists the top 5 processes consuming the most memory.

- **Logging**  
  Saves output to a log file for review.

- **Email Alerts**  
  Sends alerts to a configured email address when thresholds are exceeded.

---

## Prerequisites

1. A Linux-based operating system.
2. **mail** utility must be installed for sending email alerts.  
   Install it using:
   ```bash
   sudo apt install mailutils
   ```
3. Permissions to run shell scripts:
   ```bash
   chmod +x system_monitor.sh
   ```

---

## Usage

### Running the Script
1. Save the script as `system_monitor.sh`.
2. Execute it in the terminal:
   ```bash
   ./system_monitor.sh
   ```

### Optional Arguments
- `-t`: Set disk usage threshold (default: 80%).  
   Example:  
   ```bash
   ./system_monitor.sh -t 90
   ```

- `-f`: Specify a custom log file (default: `system_monitor.log`).  
   Example:  
   ```bash
   ./system_monitor.sh -f custom_log.log
   ```

- `-e`: Specify an email address for alerts (default: `danialnasrgerges@gmail.com`).  
   Example:  
   ```bash
   ./system_monitor.sh -e myemail@example.com
   ```

---

## Example Output

**Disk Usage Check**  
Displays partition usage and alerts if usage exceeds the threshold.  
Example:  
```
Filesystem: /dev/sda2  
Mounted on: /  
Usage: 48%  
-----------------------
WARNING: Usage on /media/danial/CDROM (100%) exceeds threshold (80%)!
```

**CPU Usage Check**  
Reports current CPU usage and alerts if it exceeds the threshold.  
Example:  
```
CPU Usage: 16.7%
```

**Memory Usage Check**  
Provides a summary of total, used, and free memory.  
Example:  
```
Total Memory: 3.8Gi  
Used Memory: 1.1Gi  
Free Memory: 2.1Gi  
```

**Top Memory-Consuming Processes**  
Lists the top 5 memory-intensive processes.  
Example:  
```
danial 5.9  /usr/bin/gnome-shell  357.875 MB
danial 0.0  /usr/libexec/evolution-data-server/evolution-alarm-notify 61.6797 MB
```

---

## Known Issues

- If the `mail` command is not installed, the script will display the error: `mail: command not found`.
- Usage thresholds should be integers. Invalid values may cause unexpected behavior.

---

## License

This project is open-source and available for use under the MIT License. Feel free to modify and redistribute.
