..
  Warning: Do not edit this file. It is automatically generated and your
  changes will be overwritten. The tool to do so lives in the
  openstack-doc-tools repository.

.. list-table:: Description of configuration options for ``[app-proxy-server]`` in ``proxy-server.conf``
   :header-rows: 1
   :class: config-ref-table

   * - Configuration option = Default value
     - Description
   * - ``account_autocreate`` = ``false``
     - If set to 'true' authorized accounts that do not yet exist within the Swift cluster will be automatically created.
   * - ``allow_account_management`` = ``false``
     - Whether account PUTs and DELETEs are even callable
   * - ``auto_create_account_prefix`` = ``.``
     - Prefix to use when automatically creating accounts
   * - ``client_chunk_size`` = ``65536``
     - Chunk size to read from clients
   * - ``conn_timeout`` = ``0.5``
     - Connection timeout to external services
   * - ``deny_host_headers`` = `` ``
     - No help text available for this option.
   * - ``error_suppression_interval`` = ``60``
     - Time in seconds that must elapse since the last error for a node to be considered no longer error limited
   * - ``error_suppression_limit`` = ``10``
     - Error count to consider a node error limited
   * - ``log_handoffs`` = ``true``
     - No help text available for this option.
   * - ``max_containers_per_account`` = ``0``
     - If set to a positive value, trying to create a container when the account already has at least this maximum containers will result in a 403 Forbidden. Note: This is a soft limit, meaning a user might exceed the cap for recheck_account_existence before the 403s kick in.
   * - ``max_containers_whitelist`` = `` ``
     - is a comma separated list of account names that ignore the max_containers_per_account cap.
   * - ``max_large_object_get_time`` = ``86400``
     - No help text available for this option.
   * - ``node_timeout`` = ``10``
     - Request timeout to external services
   * - ``object_chunk_size`` = ``65536``
     - Chunk size to read from object servers
   * - ``object_post_as_copy`` = ``true``
     - Set object_post_as_copy = false to turn on fast posts where only the metadata changes are stored anew and the original data file is kept in place. This makes for quicker posts; but since the container metadata isn't updated in this mode, features like container sync won't be able to sync posts.
   * - ``post_quorum_timeout`` = ``0.5``
     - No help text available for this option.
   * - ``put_queue_depth`` = ``10``
     - No help text available for this option.
   * - ``read_affinity`` = ``r1z1=100, r1z2=200, r2=300``
     - No help text available for this option.
   * - ``recheck_account_existence`` = ``60``
     - Cache timeout in seconds to send memcached for account existence
   * - ``recheck_container_existence`` = ``60``
     - Cache timeout in seconds to send memcached for container existence
   * - ``recoverable_node_timeout`` = ``node_timeout``
     - Request timeout to external services for requests that, on failure, can be recovered from. For example, object GET. from a client external services
   * - ``request_node_count`` = ``2 * replicas``
     - replicas Set to the number of nodes to contact for a normal request. You can use '* replicas' at the end to have it use the number given times the number of replicas for the ring being used for the request. conf file for values will only be shown to the list of swift_owners. The exact default definition of a swift_owner is headers> up to the auth system in use, but usually indicates administrative responsibilities. paste.deploy to use for auth. To use tempauth set to:
   * - ``set log_address`` = ``/dev/log``
     - Location where syslog sends the logs to
   * - ``set log_facility`` = ``LOG_LOCAL0``
     - Syslog log facility
   * - ``set log_level`` = ``INFO``
     - Log level
   * - ``set log_name`` = ``proxy-server``
     - Label to use when logging
   * - ``sorting_method`` = ``shuffle``
     - No help text available for this option.
   * - ``swift_owner_headers`` = ``x-container-read, x-container-write, x-container-sync-key, x-container-sync-to, x-account-meta-temp-url-key, x-account-meta-temp-url-key-2, x-container-meta-temp-url-key, x-container-meta-temp-url-key-2, x-account-access-control``
     - These are the headers whose conf file for values will only be shown to the list of swift_owners. The exact default definition of a swift_owner is headers> up to the auth system in use, but usually indicates administrative responsibilities. paste.deploy to use for auth. To use tempauth set to:
   * - ``timing_expiry`` = ``300``
     - No help text available for this option.
   * - ``use`` = ``egg:swift#proxy``
     - Entry point of paste.deploy in the server
   * - ``write_affinity`` = ``r1, r2``
     - This setting lets you trade data distribution for throughput. It makes the proxy server prefer local back-end servers for object PUT requests over non-local ones. Note that only object PUT requests are affected by the write_affinity setting; POST, GET, HEAD, DELETE, OPTIONS, and account/container PUT requests are not affected. The format is r<N> for region N or r<N>z<M> for region N, zone M. If this is set, then when handling an object PUT request, some number (see the write_affinity_node_count setting) of local backend servers will be tried before any nonlocal ones. Example: try to write to regions 1 and 2 before writing to any other nodes: write_affinity = r1, r2
   * - ``write_affinity_node_count`` = ``2 * replicas``
     - This setting is only useful in conjunction with write_affinity; it governs how many local object servers will be tried before falling back to non-local ones. You can use '* replicas' at the end to have it use the number given times the number of replicas for the ring being used for the request: write_affinity_node_count = 2 * replicas
