# Idle and transient validation tests

Run these tests after every `.mr` change.

## Test conditions

- Engine Simulator CE v0.1.14A
- Neutral gear
- No user throttle unless the test says otherwise
- Start from the same script each time

## Test 1 - no-throttle start

1. Hold starter.
2. Do not touch throttle.
3. Record whether the engine fires and holds idle.

Pass:

```text
Starts without throttle and remains running.
```

Fail:

```text
Requires throttle to start, or dies immediately after starter release.
```

## Test 2 - warm idle hold

1. Let the engine stabilise after starting.
2. Record idle rpm range for 30 seconds.

Current target:

```text
900 +/- 50 rpm
```

Final target later:

```text
850 +/- 50 rpm
```

## Test 3 - 1500 rpm blip

1. Raise engine to around 1500 rpm.
2. Release throttle fully.
3. Record lowest rpm and recovery time.

Pass:

```text
Does not dip below 780 rpm and recovers within about 1 second.
```

Development pass for now:

```text
Does not stall.
```

## Test 4 - 3000 rpm blip

1. Raise engine to around 3000 rpm.
2. Release throttle fully.
3. Record lowest rpm and recovery time.

Pass:

```text
Does not dip below 700 rpm and recovers within about 1.5 seconds.
```

Development pass for now:

```text
Does not stall.
```

## Test 5 - full-throttle blip

1. Briefly apply full throttle.
2. Release throttle fully.
3. Record peak rpm, lowest rpm and whether the engine catches.

Pass:

```text
Does not stall after limiter / high-rpm return.
```

## Result format

```text
Commit:
Start/no throttle:
Idle rpm:
1500 blip:
3000 blip:
Full throttle blip:
Peak hp:
Peak torque:
Notes:
```
