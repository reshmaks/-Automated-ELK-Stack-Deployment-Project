### Install Metricbeat

[Metricbeat Playbook](/Files/metricbeat-playbook.yml)

To update your Ansible playbook to install Metricbeat:

From the homepage of your ELK site:
- Click **Add Metric Data**.
- Click **Docker Metrics**.
- Click the **DEB** tab under **Getting Started** for the correct Linux instructions.

- Download the [Metricbeat `.deb` file](https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-7.4.0-amd64.deb).

- Use `dpkg` to install the `.deb` file.
- Update and copy the provided [Metricbeat config file](https://gist.githubusercontent.com/slape/58541585cc1886d2e26cd8be557ce04c/raw/0ce2c7e744c54513616966affb5e9d96f5e12f73/metricbeat).
- Run the `metricbeat modules enable docker` command.
- Run the `metricbeat setup` command.
- Run the `metricbeat -enable` command.
- Enable the Metricbeat service on boot.

To verify that your play works as expected, on the Metricbeat installation page in the ELK server GUI, scroll to **Step 5: Module Status** and click **Check Data**.

If Filebeat and Metricbeat are properly configured and launched, the result of clicking "Check data" state--"Data successfully received from this module." It means Filebeat and Metricbeat are working properly and are sending data from the DVWA servers to ELK. For more information, click on "System logs dashboard"!

![](/Images/Kibana-syslog-dashboard.png)


