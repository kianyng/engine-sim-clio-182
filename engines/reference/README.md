# Reference revisions

These files are used to preserve known-good states while the active `clio182./clio182.mr` file changes.

A revision should only be copied here when it has a useful validation result.

## rA: no-throttle-start baseline

Observed by user:

- starts without throttle
- idle around 890-920 rpm
- stable enough to build from

Known issue:

- full-throttle blip can still stall

## rB: geometry lock

Next target:

- keep rA behaviour
- lock chamber volume and compression height closer to research-backed F4R geometry
- do not touch intake, cams or throttle transient settings yet
