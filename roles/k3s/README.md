k3s
=========

Install k3s.

Example Playbook
----------------

    k3s_version: 'v1.29.0+k3s1'
    k3s_token: 'secrettoken'

    k3s_context_name: 'app'
    k3s_kubeconfig: "~/.kube/contexts/{{ k3s_context_name }}.yaml"
    k3s_api_endpoint: "{{ hostvars[groups['k3s_server'][0]]['ansible_host'] | default(groups['k3s_server'][0]) }}"
    k3s_extra_server_args: "--disable=traefik --tls-san {{ k3s_api_endpoint }}"

License
-------

MIT
