# Lynis Kernel Hardening Audit Extensions

Custom audit modules extending Lynis's `tests_kernel` suite to evaluate modern Linux attack surfaces.

## Scripts Included

- **`tests_custom_userns` (`KERN-6040`)**: Audits unprivileged user namespace restrictions (`user.max_user_namespaces`, `kernel.unprivileged_userns_clone`, and AppArmor mediation) to mitigate Local Privilege Escalation (LPE) attack surfaces.
- **`tests_custom_ebpf` (`KERN-6050`)**: Audits unprivileged eBPF access (`kernel.unprivileged_bpf_disabled`) and Just-In-Time compiler constant blinding (`net.core.bpf_jit_harden`) to mitigate in-kernel code injection and memory-spraying exploits.

## Installation

1. Copy both files into Lynis's include directory:
   ```bash
   sudo cp tests_custom_userns tests_custom_ebpf /usr/share/lynis/include/