# configs

My server configuration files for reference and reuse.

### nginx
- nginx 1.31+ with HTTP/2, HTTP/3 (QUIC), zstd + gzip compression
- Global TLS: TLS 1.2/1.3, ECDSA ciphers, X25519MLKEM768 key exchange
- Dynamic modules: `headers-more`, `zstd`, `ngx_http_acme_module`
- All reverse-proxy vhosts disable compression (`zstd off; gzip off`) to avoid
  conflicts with upstream encoding

### OpenSSH
- Ed25519 host keys and client keys only — no RSA, no ECDSA
- ML-KEM 768 + curve25519 key exchange (post-quantum hardened)
- Password authentication disabled — public key only
- All forwarding (TCP, agent, X11, tunnel) disabled
