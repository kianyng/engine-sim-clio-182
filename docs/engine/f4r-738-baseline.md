# F4R 738 baseline data

## Confirmed core specification

| Attribute | Value | Confidence | Notes |
|---|---:|---|---|
| Engine code | F4R 738 | High | Renault Clio Renaultsport 182 Cup release identifies the engine type. |
| Configuration | Inline-4, DOHC, 16-valve | High | F4R family technical material. |
| Displacement | 1,998 cc | High | Renault-published value. |
| Bore | 82.7 mm | High | Renault-published value. |
| Stroke | 93.0 mm | High | Renault-published value. |
| Compression ratio | 11.0:1 | High | Renault-published value. |
| Rated power | 182 hp DIN @ 6,500 rpm | High | Renault-published value. |
| Rated torque | 200 Nm @ 5,250 rpm | High | Renault-published value. |
| Rod length | 144 mm | Medium-high | Supported by Renault technical snippets and OE piston data. |
| Piston compression height | ~30.2 mm | Medium | Supported by OE-fit piston catalogues. |
| Crankshaft mass basis | ~14.475 kg | Medium | From Renault Sport R3 assembly material; competition context, but useful. |
| Stock flywheel mass basis | ~5.2-5.3 kg | Medium | Specialist supplier comparisons against OE flywheel. |

## Derived values

Swept volume per cylinder:

```text
499.5 cc
```

For 11.0:1 compression ratio, total clearance volume per cylinder is approximately:

```text
49.95 cc
```

This matters because Engine Simulator's `chamber_volume` should be treated as the effective trapped clearance volume, not necessarily only the raw measured pocket volume in the cylinder head.

## Important distinction

Renault Sport R3 material gives a nominal combustion chamber figure around 44.3 cc. That is useful, but it is not the same as total clearance volume. The Engine Simulator starting point should be around 50 cc because gasket volume, piston crown/valve reliefs and deck clearance all contribute to final compression.

## Values not yet proven enough to lock

- exact stock piston mass
- exact stock rod mass
- exact stock flywheel moment of inertia
- exact road F4R 738 chamber-only volume
- exact stock exhaust manifold dimensions
- exact intake runner length and plenum volume
- exact cam lobe trace
