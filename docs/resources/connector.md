---
page_title: "banyan_connector Resource - terraform-provider-banyan"
subcategory: ""
description: |-
  The connector resource allows for configuration of the connector API object. We recommend utilizing the banyansecurity/banyan-connector terraform registry module specific to your cloud provider. For more information on connector resource see the documentation https://docs.banyansecurity.io/docs/banyan-components/connector/
---

# banyan_connector (Resource)

The connector resource allows for configuration of the connector API object. We recommend utilizing the banyansecurity/banyan-connector terraform registry module specific to your cloud provider. For more information on connector resource see the [documentation](https://docs.banyansecurity.io/docs/banyan-components/connector/)

## Example Usage
```terraform
resource "banyan_api_key" "example" {
  name        = "example-connector"
  description = "api key for example connector"
  scope       = "satellite"
}

resource "banyan_connector" "example" {
  name       = "example"
  api_key_id = banyan_api_key.example.id
}
```

## Example Connector with Service Tunnel
```terraform
resource "banyan_api_key" "example" {
  name        = "example-connector"
  description = "example connector api key"
  scope       = "satellite"
}

resource "banyan_connector" "example" {
  name       = "example"
  api_key_id = banyan_api_key.example.id
  cidrs      = ["10.5.0.1/24"]
  domains    = ["example.com"]
}

resource "banyan_policy_tunnel" "example" {
  name        = "example"
  description = "some tunnel policy description"
  access {
    roles       = ["ANY"]
    trust_level = "High"
  }
}

resource "banyan_service_tunnel" "example" {
  name        = "example"
  description = "some service tunnel description"
  connectors  = [banyan_connector.example.name]
  policy      = banyan_policy_tunnel.example.id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `api_key_id` (String) ID of the API key which is scoped to satellite
- `name` (String) Name of the connector

### Optional

- `access_tiers` (Set of String) Name of the access tiers the connector will use to establish a secure dial-out connection. Will be set automatically if omitted.
- `cidrs` (Set of String) Specifies the IPv4 address ranges of your private network in CIDR notation, ex: 192.168.1.0/24. Note that you can only specify private IP address ranges as defined in RFC-1918.
- `cluster` (String) Cluster / shield name in Banyan. If not provided then the cluster will be set automatically
- `domains` (Set of String) Specifies the domains that should resolve at a DNS server in your private network, ex: mycompany.local.

### Read-Only

- `id` (String) ID of the connector in Banyan