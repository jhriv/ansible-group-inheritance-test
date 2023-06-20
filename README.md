# Ansible Group Inheritance

Proof of concept for inheriting values based upon group membership
and specification

## Sample tests

```text
❯ ansible grouper -m debug -a var=i_am
localhost | SUCCESS => {
    "i_am": "localhost"
}
❯ ansible grouper -m debug -a var=we_are
localhost | SUCCESS => {
    "we_are": "We are groupers."
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

## References

[A-Z Animals](https://a-z-animals.com/blog/discover-10-biggest-types-of-grouper-fish/)
