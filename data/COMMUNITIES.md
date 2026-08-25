# Community dataset

`communities.csv` is the source of truth for the Network page. Keep one row per city community.

## Columns

| Column | Meaning |
| --- | --- |
| `community_id` | Stable lowercase identifier; do not change after publishing. |
| `city`, `country`, `region` | Display geography used for search and grouping. |
| `status` | `active`, `forming`, or `inactive`. |
| `established_year` | Year the local community began. |
| `events_count` | Number of events organized by that community. |
| `participants_count` | Current number of people in the local community. |
| `event_attendance_total` | Cumulative attendances across events; repeat attendees count more than once. |
| `primary_focus` | One editorially selected focus used for mutually exclusive grouping. |
| `tags` | Semicolon-separated, reusable lowercase tags. |
| `data_status` | `seed` for demonstration data or `verified` after organizer review. |

## Editing rules

- Do not use commas inside values unless CSV quoting support is added to the parser.
- Separate tags with semicolons and use the same spelling across rows.
- Participant count and event attendance are different measures and should not be combined.
- Change `data_status` to `verified` only after a local organizer confirms the row.
- Add new tags sparingly; reuse an existing tag whenever it describes the community accurately.

The figures currently included are seed values for designing and testing the interface. They must be replaced or verified before being presented as official Illyrian Brains statistics.

## Professional network

`professional-groups.csv` and `professional-connections.csv` use the same model in parallel:

- A professional group is a circle sized by `participants_count`.
- A connection represents distinct people participating in both professional groups.
- `people_count` controls the connection width.
- A person counts once per professional-group pair.

Keep city and professional records separate. A person may legitimately contribute to both datasets because the two viewers answer different questions: where the network is located and what the network works on.
