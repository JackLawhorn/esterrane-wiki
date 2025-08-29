## Completed
```dataview
TABLE
FROM !"_Templates"
WHERE status AND status = "Status/#Completed"
```

## In-Progress
```dataview
TABLE
FROM !"_Templates"
WHERE status AND status = "#Status/InProgress"
```

## Mentioned but not created
```dataview

TABLE
FLATTEN file.outlinks as Note
WHERE !(Note.file) AND !contains(meta(Note).path, "/") AND !contains(file.path, "Upcoming")
GROUP by Note
SORT file.name ASC

```
