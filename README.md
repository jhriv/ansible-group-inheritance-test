# Ansible Group Inheritance

Proof of concept for inheriting values based upon group membership
and specification

## Sample tests

### Flattened

```text
❯ ansible grouper -m debug -a var=i_am
localhost | SUCCESS => {
    "i_am": "localhost"
}
❯ ansible grouper -m debug -a var=we_are
localhost | SUCCESS => {
    "we_are": "a type of saltwater fish that belongs to the family Serranidae."
}
❯ ansible grouper -m debug -a var=color_name
localhost | SUCCESS => {
    "color_name": "red"
}
❯ ansible grouper -m debug -a var=location_name
localhost | SUCCESS => {
    "location_name": "Warsaw"
}
❯ ansible nassau -m debug -a var=location_name
localhost | SUCCESS => {
    "location_name": "Warsaw"
}
```

## Aliased

```text
❯ ansible grouper -m debug -a var=we_are -i inventories/aliased
black_grouper | SUCCESS => {
    "we_are": "a type of saltwater fish that belongs to the family Serranidae."
}
...
❯ ansible grouper -m debug -a var=color_name -i inventories/aliased
black_grouper | SUCCESS => {
    "color_name": "black"
}
...
❯ ansible grouper -m debug -a var=location_name -i inventories/aliased
black_grouper | SUCCESS => {
    "location_name": "unspecified"
}
...
❯ ansible nassau -m debug -a var=location_name -i inventories/aliased
nassau_grouper | SUCCESS => {
    "location_name": "Nassau"
}
```

For some fun facts, try `ansible all -m debug -a var=i_am -i inventories/aliased`

## Inventory in YAML Format

The aliased inventory is provided as an example in YAML format.

## References

[A-Z Animals](https://a-z-animals.com/blog/discover-10-biggest-types-of-grouper-fish/)
