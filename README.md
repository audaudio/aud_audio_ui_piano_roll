# aud_audio_ui_piano_roll

English | [Deutsch](README.de.md)

[![CI](https://github.com/audaudio/aud_audio_ui_piano_roll/actions/workflows/quick_check.yaml/badge.svg)](https://github.com/audaudio/aud_audio_ui_piano_roll/actions/workflows/quick_check.yaml)

Piano roll widget of the Audanika Audio Engine, modeled on AudioKit PianoRoll.
Pure Flutter, free of the engine; part of the Audanika Audio Engine, planned
in [aud_audio_pm](https://github.com/audaudio/aud_audio_pm).

## Motivation

- The sequencer of the Audanika Audio Engine plays note sequences; its users
  need to see and edit them on every platform Flutter supports
- AudioKit PianoRoll shows a small, proven, MIT-licensed note model and a
  canvas that edits it; the package ports them instead of inventing a new one
- The widget renders and edits a Dart model and emits edits as callbacks
  (decision ui-001), so it tests headless and works with any sequencer state

## Installation

The package is not published to pub.dev; add it from its git tags:

```yaml
dependencies:
  aud_audio_ui_piano_roll:
    git:
      url: git@github.com:audaudio/aud_audio_ui_piano_roll.git
      tag_pattern: '{{version}}'
    version: ^0.0.3
```

## Usage

The package is a placeholder: the widget follows with step S17 of the plan of
the Audanika Audio Engine (see [Status](#status)). Until then it exports
nothing but the boilerplate of the Flutter package template, so this is all
that runs:

```dart
import 'package:aud_audio_ui_piano_roll/aud_audio_ui_piano_roll.dart';

void main() {
  // The widget is not built yet; the package exports the boilerplate
  // Calculator of the Flutter package template until it arrives.
  print(Calculator().addOne(1));
}
```

```text
2
```

## Limitations

- No widget yet; see [Status](#status)
- The widget will not depend on the engine (decision ui-003): apps bind it
  through `aud_audio_ui_bindings`, plugin editors through their shell's
  protocol

## Documentation

- [Plan 17: Audanika Audio
  Engine](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/tickets/2026-10-07-17-audanika-audio-engine.md),
  which plans the package as step S17
- The decisions
  [ui-001](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/concepts/decisions/ui-001.md)
  (UI packages are Flutter widgets over Dart models) and
  [ui-003](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/concepts/decisions/ui-003.md)
  (the engine adapters live in a binding package)
- [AudioKit PianoRoll](https://github.com/AudioKit/PianoRoll), the template
  (MIT)
- The guides in [`doc/guides`](doc/guides) and the blog posts in
  [`doc/blog`](doc/blog)

## Status

Before 1.0 — the API may change between minor versions. The repo holds the
boilerplate of a Flutter package and its version constant only. Step S17
builds the note model (notes with start, length and pitch) ported from
AudioKit PianoRoll, the canvas, the editing of notes and an adapter to the
sequences of `aud_audio_sequencer`. The package depends on
`aud_audio_sequencer` for that.

## Contributing

Tickets run through the `gg` workflow: see the [Develop
Guide](doc/guides/develop-guide.md) and the [Review
Guide](doc/guides/for-ai/ai-review-guide.md).

## License

MIT — see [LICENSE](LICENSE).
