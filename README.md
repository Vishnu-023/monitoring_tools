
# Monitoring of Resource

Monitoring involves the process of observing and measuring the performance, health, and behavior of systems, applications, infrastructure, or any other environment to ensure that they are functioning as expected.

#
Node Exporter is a component of the Prometheus monitoring system, which is used to collect various system-level metrics from Linux/Unix-based machines and make them available for monitoring and alerting. 
NOTE: node exporter is to be installed on machine that should be monitered
#
Grafana is an open-source data visualization and monitoring tool that allows you to create interactive and customizable dashboards for monitoring and analyzing data from various sources. It's widely used in IT operations, software development, and various industries to gain insights from data and make informed decisions.
NOTE:to be installed in sepearate machine
#
Prometheus is an open-source monitoring and alerting toolkit that specializes in collecting and storing time-series data from various sources, allowing you to monitor the performance and health of systems, applications, and services. 
NOTE:to be installed in sepearate machine






## Installation

#### Install Node Exporter on host machine which needs to be tracked. copy files to local machine from git repo and run the shell script. to access port <ip>:9100 port

```http
  ./NodeExporter.sh 
```
#### Install Prometheus(monietring machine)  on host machine which needs to be tracked. copy files to local machine from git repo and run the shell script.to access port <ip>:9090 port. NOTE: update ports in prometheus.yml file (target - ["<ip>:9100", "<ip>:9100"])

```http
  ./prometheus.sh 
```

#### Install Grafana (monietring machine)  on host machine which needs to be tracked. copy files to local machine from git repo and run the shell script. to access port <ip>:3000 port

```http
  ./grafana.sh 
```

## steps to  configure alerts in grafana on slack 
To configure alerts in Grafana to send notifications to Slack, you need to set up a notification channel for Slack and then associate that channel with your alert rules. Here's a step-by-step guide to help you through the process:

1. Set Up a Slack Incoming Webhook:
Before you can configure Slack notifications in Grafana, you need to create an incoming webhook in your Slack workspace. Here's how:

Go to your Slack workspace and navigate to "Settings & administration" > "Manage apps."
Search for "Incoming Webhooks" and click on "Add to Slack" to install the app.
Follow the prompts to set up a new webhook for the desired channel in your workspace. This will provide you with a webhook URL that you'll use in Grafana.

2. Configure Slack Notification Channel in Grafana:

Log in to your Grafana instance.
Click on the gear icon (configuration) in the side menu and select "Notification channels."
Click on "Add channel" and choose "Slack."
Provide a name for the channel and paste the Slack webhook URL you obtained in the previous step.
Save the notification channel.

3. Associate the Notification Channel with an Alert Rule:

Create or open a dashboard in Grafana that contains the panel you want to set alerts on.
Edit the panel and navigate to the "Alert" section as described in the previous response.
Click on "Create Alert."
Configure the alert conditions based on your metric data.
In the "Notifications" section, click on "Add new notification channel."
Select the Slack notification channel you previously configured.
Customize the message template and settings for Slack notifications (you can use placeholders to include dynamic information in the notification).
Save the alert rule settings.

4. Test the Alert:

To test the alert, you can use the "Test Rule" option in the alert configuration section.
This will simulate the alert being triggered and send a test notification to your configured Slack channel.

5. Save and Enable the Alert:

After configuring and testing the alert rule, save the panel settings.
Ensure that the "Alerting" feature is enabled for the dashboard.
Grafana will now start evaluating the alert conditions based on the configured frequency and criteria. When conditions are met, notifications will be sent to the configured Slack channel.

NOTE: Alert for Ec2 instance if CPU ultilization is more than 80%, we have to give alrerts as ec2 instance select ec2 instance(rule A) --> select Rule B (thrushold of A) >(morethan) 80% --> save the rule   


## Authors

- [Vishnu_hiral, Wajid_anwar ,Imran , Syed_Asifulla]

