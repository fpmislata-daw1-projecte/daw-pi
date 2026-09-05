---
title: Calendari
icon: material/calendar
alias: calendari
---
# :material-calendar: Calendari

!!! warning "Aquest calendari és provisional i pot ser modificat."

/// calendar
start = 2026-09-01
end = 2027-06-30
locale = "ca"
size = "md"

[holiday]
tooltip = "No lectiu"
dates = [
  [2026-10-09, 2026-10-12],
  [2026-12-07, 2026-12-08],
  [2026-12-23, 2027-01-06],
  [2027-03-16, 2027-03-19],
  [2027-03-25, 2027-04-05],
  2027-06-24,
]

\[[ranges]]
from = 2027-02-01
to = 2027-02-14
class = "green"
tooltip = "Sprint 1"
exclude = ["weekends", "holidays"]

\[[ranges]]
from = 2027-02-15
to = 2027-02-28
class = "blue"
tooltip = "Sprint 2"
exclude = ["weekends", "holidays"]

\[[ranges]]
from = 2027-03-01
to = 2027-03-31
class = "yellow"
tooltip = "Sprint 3"
exclude = ["weekends", "holidays"]

\[[ranges]]
from = 2027-04-06
to = 2027-04-16
class = "orange"
tooltip = "Sprint 4"
exclude = ["weekends", "holidays"]

\[[ranges]]
from = 2027-04-19
to = 2027-04-30
class = "red"
tooltip = "Sprint 5"
exclude = ["weekends", "holidays"]

\[[ranges]]
from = 2027-05-03
to = 2027-05-14
class = "purple"
tooltip = "Sprint 6"
exclude = ["weekends", "holidays"]

\[[days]]
date = 2027-02-12
class = "exam-day"
tooltip = "Presentació Sprint 1"
override = true

\[[days]]
date = 2027-02-26
class = "exam-day"
tooltip = "Presentació Sprint 2"
override = true

\[[days]]
date = 2027-03-24
class = "exam-day"
tooltip = "Presentació Sprint 3"
override = true

\[[days]]
date = 2027-04-16
class = "exam-day"
tooltip = "Presentació Sprint 4"
override = true

\[[days]]
date = 2027-04-30
class = "exam-day"
tooltip = "Presentació Sprint 5"
override = true

\[[days]]
date = 2027-05-14
class = "exam-day"
tooltip = "Presentació Sprint 6"
override = true
///
/// figure-caption
Calendari del curs 2026-2027.
///

<style>
.md-calendar-day.exam-day { background: #d23f31; color: #fff; font-weight: 700; }
.md-calendar-tooltip-item.exam-day::before { background: #d23f31; }

table.calendari-sprints {
  border-collapse: collapse;
}
table.calendari-sprints td,
table.calendari-sprints th {
  border: 1px solid var(--md-default-fg-color--lightest);
  padding: 5px 10px;
  vertical-align: middle;
  text-align: left;
}
table.calendari-sprints th {
  background-color: var(--md-primary-fg-color);
  color: var(--md-primary-bg-color);
  text-align: center;
  font-weight: bold;
}
.sprint-badge {
  display: inline-block;
  padding: 0.1rem 0.6rem;
  border-radius: 999px;
  margin-right: 0.4rem;
}
</style>

<div class="center">
<table class="calendari-sprints">
<thead>
<tr><th>Sprint</th><th>Data</th></tr>
</thead>
<tbody>
<tr><td><span class="sprint-badge" style="background-color: var(--md-cal-hue-green-bg); color: var(--md-cal-hue-green-fg);">Sprint 1</span></td><td>01/02/2027 – 14/02/2027</td></tr>
<tr><td><span class="sprint-badge" style="background-color: var(--md-cal-hue-blue-bg); color: var(--md-cal-hue-blue-fg);">Sprint 2</span></td><td>15/02/2027 – 28/02/2027</td></tr>
<tr><td><span class="sprint-badge" style="background-color: var(--md-cal-hue-yellow-bg); color: var(--md-cal-hue-yellow-fg);">Sprint 3</span></td><td>01/03/2027 – 31/03/2027</td></tr>
<tr><td><span class="sprint-badge" style="background-color: var(--md-cal-hue-orange-bg); color: var(--md-cal-hue-orange-fg);">Sprint 4</span></td><td>06/04/2027 – 16/04/2027</td></tr>
<tr><td><span class="sprint-badge" style="background-color: var(--md-cal-hue-red-bg); color: var(--md-cal-hue-red-fg);">Sprint 5</span></td><td>19/04/2027 – 30/04/2027</td></tr>
<tr><td><span class="sprint-badge" style="background-color: var(--md-cal-hue-purple-bg); color: var(--md-cal-hue-purple-fg);">Sprint 6</span></td><td>03/05/2027 – 14/05/2027</td></tr>
</tbody>
</table>
</div>
/// figure-caption
Distribució temporal dels sprints.
///
