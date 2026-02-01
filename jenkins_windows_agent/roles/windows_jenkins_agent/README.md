# windows_jenkins_agent

This role installs and runs a Jenkins agent on a Windows machine as a Windows
service using NSSM (Non-Sucking Service Manager).

## What this role does
- Creates a Jenkins agent directory
- Downloads agent.jar from Jenkins
- Downloads and configures NSSM
- Registers the Jenkins agent as a Windows service
- Starts the service automatically

## Requirements
- Windows host
- Java installed on the Windows host
- WinRM connectivity from Ansible Controller

## Role Variables

### Required
| Variable | Description |
|--------|-------------|
| jenkins_url | Jenkins controller URL |
| jenkins_agent_name | Jenkins node name |
| jenkins_agent_secret | Jenkins agent secret |

### Optional
| Variable | Default |
|--------|---------|
| jenkins_agent_dir | C:\\Jenkins |
| jenkins_agent_service_name | JenkinsAgent |

## Example Playbook

```yaml
- hosts: windows
  roles:
    - henryorg.jenkins_windows_agent.windows_jenkins_agent
