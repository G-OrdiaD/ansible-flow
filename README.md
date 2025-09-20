# Ansible Infrastructure Automation for DevOps with AWS

This repository contains Ansible playbooks and roles for automating infrastructure deployment and management, created during the DevOps with AWS course.

## Project Structure

```
.
├── playbooks/                 # Ansible playbooks for various deployments
├── roles/                     # Custom Ansible roles for specialized configurations
├── inventory/                 # Environment-specific inventory files
│   ├── development            # Development environment hosts
│   ├── hosts.ini             # Main inventory file
│   ├── production            # Production environment hosts
│   ├── staging               # Staging environment hosts
│   └── testing               # Testing environment hosts
├── ansible.cfg               # Ansible configuration settings
├── dynamic-template.j2       # Jinja2 template for dynamic content
├── requirements.yml          # External role and collection dependencies
└── README.md                 # Project documentation
```

## Quick Start

### Prerequisites
- Python 3.6+
- SSH access to target servers

### Installation
**Install Ansible:**
```bash
# For Ubuntu/Debian:
sudo apt install ansible

# For Amazon Linux:
sudo dnf install ansible
```

### Configuration
1. **Set up inventory:**
   ```bash
   cp inventory/hosts.ini.example inventory/hosts.ini
   # Edit inventory/hosts.ini with your server details
   ```

2. **Install required roles and collections:**
   ```bash
   ansible-galaxy install -r requirements.yml
   ```

### Usage
Run a playbook:
```bash
ansible-playbook -i inventory/hosts.ini playbooks/01-basic-server-setup.yml
```

## Playbooks

The playbooks are organized by infrastructure component:

| Category | Playbooks |
|----------|-----------|
| **Infrastructure Setup** | `basic-server-setup.yml`, `webserver-deployment.yml` |
| **Application Deployment** | `application-deployment.yml`, `api-backend.yml` |
| **Database Services** | `database-setup.yml` |
| **Infrastructure Services** | `load-balancer-config.yml`, `monitoring-setup.yml` |
| **Content Management** | `static-content-deploy.yml`, `dynamic-content-deploy.yml` |
| **Special Operations** | `maintenance-mode.yml`, `multi-platform-deploy.yml` |

## Roles

Custom Ansible roles for specialized server configurations:

- **App Server**: Application runtime environments and dependencies
- **Database**: Database installation, configuration, and management
- **Load Balancer**: Traffic distribution and high availability setup
- **Monitoring**: Health checks, metrics collection, and alerting
- **Web Server**: HTTP server configuration and content delivery

## Requirements

Dependencies are specified in `requirements.yml`:
- External Ansible Galaxy roles
- Collection dependencies for AWS integration
- Version-pinned requirements for consistent environments

## Author

**ORDIA DAVID GBAKENA**  
DevOps Engineer

## License

This project is for educational purposes as part of the DevOps with AWS course.