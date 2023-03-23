# setup-tailscale-ssh

This is an action composite to setup ssh acess through tailscale. Usage example:

```
name: Test action

on:
  workflow_dispatch:

jobs:
  diagrammar_width_checks:
    runs-on: ubuntu-20.04
    steps:
      - uses: brilliantorg/setup-tailscale-ssh@v1
        with:
          ts-api-client-id: ${{ secrets.TS_API_CLIENT_ID }}
          ts-api-client-secret: ${{ secrets.TS_API_CLIENT_SECRET }}
          ssh-private-key: ${{ secrets.DEPLOYER_LAN_PRIVATE_SSH_KEY }}

      - name: run some command
        run: |
          ssh brilliant-server-f1 /some/command args
```
