# Validation log - M2.1 limiter-only experiment

## Tested script

```text
clio182./clio182.mr
```

Commit under test:

```text
554ce5cdd5ab6e8bc0884d2231c08eb4ab81ca34
```

## User-observed result

```text
Idle: around 810-900 rpm
1500 rpm blip: drops to around 700 rpm and stabilises
3000 rpm blip: drops to around 600 rpm and stabilises
4000 rpm blip: stalls
Full-throttle blip: stalls
```

## Interpretation

The shorter limiter cut did not solve the stall, and the engine stalls from a 4000 rpm blip without needing to hit the limiter. This rules out limiter cut duration as the primary cause.

The likely problem area is now transient intake/airflow behaviour rather than idle timing, basic ignition, or limiter duration.

## Next action

Start a controlled intake-system experiment. The current intake values are inherited from the stable baseline and are not physically representative of the Clio 182 manifold. The first intake experiment should reduce the oversized 4.5 L plenum while leaving cams, head flow, inertia and ignition alone.
