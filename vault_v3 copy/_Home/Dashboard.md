# My Vault Dashboard

## 🚀 Active Projects

```base
views:
  - type: table
    name: All Active
    filters:
      and:
        - '!file.name.contains("Template")'
        - type.contains("project")
        - status.contains("active")
    order:
      - file.name
      - type
      - updated
    columnSize:
      note.type: 95

```

## x
```base
filters:
  and:
    - file.hasTag("x")
views:
  - type: table
    name: x
    order:
      - file.name
      - updated
    columnSize:
      file.name: 182

```

## x
```base
filters:
  and:
    - file.hasTag("x")
views:
  - type: table
    name: x
    order:
      - file.name
      - updated
    columnSize:
      file.name: 182

```

## x
```base
filters:
  and:
    - file.hasTag("x")
views:
  - type: table
    name: x
    order:
      - file.name
      - updated
    columnSize:
      file.name: 182

```

x
```base
filters:
  and:
    - file.hasTag("X")
views:
  - type: table
    name: x
    order:
      - file.name
      - updated
    columnSize:
      file.name: 182

```


Cheatsheets
```base
views:
  - type: table
    name: Cheatsheets
    filters:
      and:
        - '!file.name.contains("Template")'
        - file.tags.contains("cheatsheet")
    order:
      - file.name
      - type
      - updated
    columnSize:
      note.type: 95

```


````yaml
```base
views:
  - type: table
    name: All Active
    filters:
      and:
        - '!file.name.contains("Template")'
        - file.tags.contains("cheatsheet")
    order:
      - file.name
      - type
      - updated
    columnSize:
      note.type: 95
```
````

