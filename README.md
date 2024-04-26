# Installing Prometheus Server on Linux Ubuntu 22.04 as a Service

## Overview
This project automates the installation process of Prometheus Server on a Linux Ubuntu 22.04 system. It includes downloading Prometheus, setting up configuration files, creating necessary directories, configuring systemd service, and starting Prometheus as a service.

## Steps:

1. **Execute Installation Script:**
  
   - Make the installation script executable with the command: `chmod +x install_prometheus_ubuntu.sh`.
   - Run the installation script with superuser privileges using the command: `sudo bash install_prometheus_ubuntu.sh`.

 ### Script Start
3. **Installation Script Execution:**
   - The script will automatically download the desired version of Prometheus from GitHub.
   - It will extract the downloaded tarball and move the Prometheus binary to `/usr/bin/` for system-wide access.
   - Temporary files will be cleaned up after the installation.

4. **Configuration:**
   - Directories for Prometheus configuration (`/etc/prometheus`) and time-series data storage (`/etc/prometheus/data`) will be created.
   - A basic configuration file (`prometheus.yml`) will be generated for Prometheus.

5. **User and Permissions:**
   - A system user named `prometheus` with restricted shell access will be created.
   - Ownership of relevant directories and files will be assigned to the `prometheus` user and group.

6. **Systemd Service Configuration:**
   - A systemd service unit file (`prometheus.service`) will be created.
   - The service will be configured to run as user `prometheus`.
   - Automatic restart on failure will be enabled for the service.
   - Prometheus server will be started with its configuration file and data storage path specified.

7. **Systemd Management:**
   - Systemd will be reloaded to load the newly added service unit.
   - Prometheus service will be started and enabled to automatically start at system boot.
 ### Script End

8. **Verification:**
   - The status of the Prometheus service can be checked using the command: `systemctl status prometheus`.
   - The installed Prometheus version can be verified by running the command: `prometheus version`.

## Results:
Upon completion of the script execution, Prometheus Server will be installed and configured on the Linux Ubuntu 22.04 system. It will be running as a systemd service, ensuring that it starts automatically upon system boot and is managed by the system. Additionally, the status of the Prometheus service can be checked, and the installed version can be verified manually.

Please see below for screenshots of the execution of verification commands:

![Prometheus Service Status](https://github.com/DimitryZH/installing-prometheus-server/assets/146372946/bc95ee53-b52a-4ff0-914c-8fa6cf0a5720)

## Conclusion:
This project provides a streamlined and automated approach to installing Prometheus Server on Linux Ubuntu 22.04, allowing for easy monitoring and metrics collection on the system. By configuring Prometheus as a systemd service, it ensures reliability and ease of management, making it suitable for production environments.
