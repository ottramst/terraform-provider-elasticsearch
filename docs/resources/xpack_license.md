---
layout: "elasticsearch"
page_title: "Elasticsearch: elasticsearch_license"
subcategory: "Elasticsearch Xpack"
description: |-
  Provides an Elasticsearch xpack license resource.
---

# elasticsearch_license

Provides an Elasticsearch xpack license resource.

## Example Usage

```tf
# Create an xpack basic license
resource "elasticsearch_license" "basic" {
  use_basic_license = "true"
}

resource "elasticsearch_license" "enterprise" {
  license = <<EOF
  {"uid":"893361dc-9749-4997-93cb-802e3d7fa4xx","type":"basic","issue_date_in_millis":1411948800000,"expiry_date_in_millis":1914278399999,"max_nodes":1,"issued_to":"issuedTo","issuer":"issuer","signature":"xx"}
EOF
}
```

## Argument Reference

The following arguments are supported:

* `license` - (Optional) The JSON string of the enterprise license file.
* `use_basic_license` - (Optional) Boolean, whether to use a basic license, cannot be used with `license`.

## Attributes Reference

The following attributes are exported:

* `id` - The unique identifier of the xpack license as returned by the Elasticsearch API.
