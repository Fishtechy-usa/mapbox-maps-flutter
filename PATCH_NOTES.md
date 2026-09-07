# Flytechy terrain removal patch

Based on upstream v2.28.4 (native Android/iOS 11.28.4). The upstream LICENSE applies.

Changes:
- Add `StyleManager.removeStyleTerrain()` on the existing per-map Pigeon channel.
- iOS calls native `removeTerrain()`, which passes a null terrain rather than an empty dictionary.
- Android passes `Value.nullValue()` to native `setStyleTerrain` and propagates errors.
- Drop `resolution: workspace` so the package resolves as a git dependency.

Upstream's published package does not include its Pigeon input schema, so the
generated Dart, Kotlin and Swift protocol files carry this operation by hand.
Keep it in all three when regenerating against a newer upstream.
