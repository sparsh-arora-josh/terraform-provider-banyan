---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "banyan_accesstier_group Resource - terraform-provider-banyan"
subcategory: ""
description: |-
  The access tier group resource allows for configuration of the access tier group API object.
---

# banyan_accesstier_group (Resource)

The access tier group resource allows for configuration of the access tier group API object.



<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `cidrs` (Set of String) CIDR range
- `cluster` (String) Cluster / shield name in Banyan
- `dns_search_domains` (String)
- `domains` (Set of String) Any internal domains that can only be resolved on your internal network’s private DNS
- `keepalive` (Number) Keepalive
- `name` (String) Name of the access tier group
- `shared_fqdn` (String) Shared FQDN
- `udp_port_number` (Number) UDP port

### Optional

- `attach_access_tier_ids` (Set of String) Access tier IDs to attach to access tier group
- `console_log_level` (String) Controls verbosity of logs to console. Must be one of "ERR", "WARN", "INFO", "DEBUG"
- `debug_address_transparency` (Boolean) Provide client address transparency
- `debug_client_timeout` (Number) Client identification timeout
- `debug_code_flow` (Boolean) Enable or disable OpenID Connect
- `debug_cpu_profile` (String) Output file for CPU profiling; may impact performance. If empty, this is disabled
- `debug_disable_docker` (Boolean) Disable Docker monitoring
- `debug_full_server_cert_chain` (Boolean) Include non-root (intermediate) CA certs during TLS handshakes
- `debug_host_only` (Boolean) Host only mode
- `debug_http_backend_log` (Boolean) Verbose logging for HTTP backend traffic
- `debug_inactivity_timeout` (Number) HTTP inactivity timeout
- `debug_keep_alive` (Boolean) Enable TCP keepalive messages for TCP sockets handled by Netagent
- `debug_keep_count` (Number) Number of missing TCP keepalive acknowledgements before closing connection
- `debug_keep_idle` (Number) Idle time before sending a TCP keepalive
- `debug_keep_interval` (Number) Time between consecutive TCP keepalive messages
- `debug_mem_profile` (Boolean) Output file for memory profiling; may impact performance. If empty, this is disabled
- `debug_period` (Number) Interval for reporting statistics
- `debug_request_level_events` (Boolean) Generate access events at the request level
- `debug_send_zeros` (Boolean) Send all-zero data points to Shield
- `debug_service_discovery_enable` (Boolean) Enable or disable DNS and conntrack logging
- `debug_service_discovery_msg_limit` (Number) Message threshold for batch processing
- `debug_service_discovery_msg_timeout` (Number) Timeout value for service discovery batch processing
- `debug_shield_timeout` (Number) If Shield is not available, policies will be treated as if they are permissive. Zero means this is disabled.
- `debug_use_rsa` (Boolean) Netagent will generate RSA instead of ECDSA keys
- `debug_visibility_only` (Boolean) Enable or disable visibility mode. If on, Netagent will not do policy enforcement on inbound traffic
- `description` (String) Description of access tier group
- `detach_access_tier_ids` (Set of String) Access tier IDs to detach from access tier group
- `dns_enabled` (Boolean) Enable DNS for service tunnels (needed to work properly with both private and public targets)
- `enable_hsts` (Boolean) If enabled, Banyan will send the HTTP Strict-Transport-Security response header
- `event_key_rate_limiting` (Boolean) Enable rate limiting of Access Event generation based on a credit-based rate control mechanism
- `events_rate_limiting` (Boolean) Enable rate limiting of Access Event generation based on a credit-based rate control mechanism
- `file_log` (Boolean) Whether to log to file or not
- `file_log_level` (String) Controls verbosity of logs to file. Must be one of "ERR", "WARN", "INFO", "DEBUG"
- `forward_trust_cookie` (Boolean) Forward the Banyan trust cookie to upstream servers. This may be enabled if upstream servers wish to make use of information in the Banyan trust cookie.
- `infra_maximum_session_timeout` (Number) Timeout in seconds infrastructure sessions connected via the access tier
- `log_num` (Number) For file logs: Number of files to use for log rotation
- `log_size` (Number) For file logs: Size of each file for log rotation
- `statsd_address` (String) Address to send statsd messages: “hostname:port” for UDP, “unix:///path/to/socket” for UDS

### Read-Only

- `id` (String) ID of the access tier group in Banyan
