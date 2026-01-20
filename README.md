# MDE Ansible Role

Self-contained role for Microsoft Defender for Endpoint deployment.

## Setup

1. **Get MDE files** from https://security.microsoft.com:
   - Settings > Endpoints > Onboarding > Windows (preview)
   - Download package

2. **Place files** in `files/` directory:
   - `DefenderDT.exe`
   - `WindowsDefenderATP.onboarding`

3. **Run deployment**:
   ```bash
   ansible-playbook -i inventory.ini deploy.yml
   ```

## Options

Change `mde_options` to customize:

```yaml
# Standard
mde_options: "-Quiet"

# Allow reboot
mde_options: "-Quiet -AllowReboot" 

# Server passive mode
mde_options: "-Quiet -Passive"

# With proxy
mde_options: "-Quiet -Proxy:proxy.company.com:8080"

# Update only
mde_options: "-UpdateOnly -Quiet"

# Offboard
mde_options: "-Offboard -YES -Quiet"
```

## Structure

```
mde_role/
├── tasks/main.yml     # Installation logic
├── defaults/main.yml  # Default settings
├── files/            # PUT MDE FILES HERE
│   └── README.txt    # Instructions
└── README.md         # This file
```

Simple and self-contained!
