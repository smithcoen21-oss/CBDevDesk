# Security notes

Treat project members, uploads, repositories and terminal commands as untrusted. Never mount Docker socket into the API or collaboration service. Untrusted execution requires a separate worker boundary with non-root execution, CPU/memory/PID/disk/time limits, syscall policy, network egress controls, ephemeral storage and image allowlisting. Use short-lived Git credentials and an external secret manager in production. Test every project operation for cross-tenant access.
