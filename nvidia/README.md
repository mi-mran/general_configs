# Mac-related tips, issues and fixes

## Monitoring GPU Usage (Spot Values)
```bash
$ nvidia-smi
```
If constant monitoring is required, use the following command instead (for Linux systems):

```bash
$ watch -n10 nvidia-smi
```

This example refreshes the `nvidia-smi` command every 10 seconds. Replace `10` if necessary.