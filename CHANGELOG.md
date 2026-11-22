# Changelog

## 1.0.0 — first public release

- Set the public application and package version to 1.0.0.
- Package the Windows desktop app as a portable ZIP; no Python installation is needed to run it.
- Document local model routing, benchmarking, Community Model Cards, permission-gated file operations, and current limitations.

## 0.7.3b1 — development history

- Add offline Community Cards for one-observation export and import, with a reviewable privacy preview, strict validation, separate `UNVERIFIED` Community Evidence storage, duplicate detection, and no routing effect.
- Harden display of imported untrusted card text.
- Correct Windows `German_Switzerland` locale recognition and classify explicit named-file write requests with an exact controller-owned WriteScope; educational questions remain read-only.
- Add isolated two-installation Experience and Community Card regression tests.
- Ask worker and planner prompts to use the current request language while preserving literal text, code, paths, and response contracts.
- Recognize common programming-language source files consistently in routing, generation requests, workspace discovery, and source-scope resolution. Keep automatic verification limited to the existing Python and Godot checks.
- Localize the main workspace, core memory/activity labels, settings, permissions, and Community Cards in DE/EN/FR; require restart after a UI-language change to avoid mixed-language windows.
- Remove the unused Semantic Resolver multilingual toggle while preserving its saved value for configuration compatibility.
- At that point, Project Builder, model qualification, and remaining advanced-screen localization were still experimental; see Known Limitations and the Community Cards guide.
- The recorded regression suite at that point reported 1,118 passed, 0 failed, 5 skipped.


## 0.7.1

Explicit project Memory work, deterministic English remember and bounded single-record forget.

## 0.7.0

Clean source baseline, initial localization work, atomic diagnostic export preservation and English developer documentation built on the v0.6.9.4 behavior. Localization remains partial and experimental. An optional image with unconfirmed redistribution rights has been excluded from the public candidate.

## 0.6.9.4

Bounded compound task and continuity repairs; atomic redacted diagnostic ZIP export.
