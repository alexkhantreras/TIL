# Terraform

<br/> <br/>

## For loops with a filter
Terraform for loops allow us to iterate through objects. Paired with an `if` condition, they can be used to filter objects.

Assuming a list of pg instances with detailed properties is defined elsewhere we can create a `resource_parent.resource-property`
resource for only those pg instance with a non-empty-string value of `property_name`.

```terraform
resource "resource_parent" "resource-property" {
  for_each  = { for pg_instance, instance in var.pg-instances : pg-instance => instance if instance.property != "" }
  name      = "provider.property_name"
  value     = each.value["property_name"]
}
```

The `for_each` evaluates a map, returning key-value pairs from the input that meet the condition. A more general example would be,

```terraform
for_each  = { for key, value in iterable : key => value if value.property != "" }
```

<br/> <br/>


## Target specific resources
When running `terraform [command]` we can target specific resources with the `-target` flag

```terraform
resource "resource_parent" "resource-property" {
  for_each  = { for pg_instance, instance in var.pg-instances : pg-instance => instance if instance.property != "" }
  name      = "provider.property_name"
  value     = each.value["property_name"]
}
```

To target the above example resource we would run

```bash
terraform [environment] [command] -target=resource_parent.resource-property
```
