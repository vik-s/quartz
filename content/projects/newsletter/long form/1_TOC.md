## Ongoing Articles
```dataview
TABLE without id tags,rows.file.link as "Title"
FROM "projects/newsletter/long form"
WHERE project = "substack"
WHERE status = "🚧"
FLATTEN tags
GROUP BY tags
```

## Completed Articles
```dataview
TABLE WITHOUT ID tags,rows.file.link as "Title", rows.date_published as "Published"
FROM "projects/newsletter/long form"
WHERE project = "substack"
WHERE status = "🟢"
FLATTEN tags
GROUP BY tags
```

## Ideas
```dataview
TABLE without id tags,rows.file.link as "Title"
FROM "projects/newsletter/long form"
WHERE project = "substack"
WHERE status != "🟢" AND status != "🚧"
FLATTEN tags
GROUP BY tags
```


















