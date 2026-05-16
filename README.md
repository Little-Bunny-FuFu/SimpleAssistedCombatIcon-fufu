# SimpleAssistedCombatIcon-fufu

A personal fork of [**SimpleAssistedCombatIcon**](https://github.com/katur239/SimpleAssistedCombatIcon)
by **Katur239**. All credit for the addon goes to them — this fork exists
only to carry a handful of targeted keybind-display fixes while they are
reviewed upstream.

> **Upstream bug report** (full root-cause analysis + suggested patches for
> every change here):
> [katur239/SimpleAssistedCombatIcon#20](https://github.com/katur239/SimpleAssistedCombatIcon/issues/20)

If/when the original addon incorporates these fixes, **use the original** —
this fork is not intended to compete with or replace it.

## What this fork changes

Each change is tagged with a `-- fufu:` comment and was verified against
Blizzard's `Blizzard_ActionBar` source, `LibActionButton-1.0`, and
Bartender4's source.

1. **Conditional / multi-spell macros now show a keybind** — adds a
   `GetMacroSpell` fallback when a macro's `GetActionInfo` `subType` isn't
   `"spell"` (previously such macros resolved to nothing).
2. **Bartender4 bars 2 & 7–11 (incl. Class Bars) fixed** — buttons are keyed
   by Bartender4's *global* `BT4Button{slot}` name instead of a colliding
   per-bar index.
3. **Renamed Bartender4 builds detected** — detection also keys off the
   `_G.Bartender4` global, so forks/rebrands are recognised.
4. **All bound keys read** — up to 4 `GetBindingKey` results, not just the
   first; key type-guarded.
5. **"Prefer Mouse / Modifier Binding"** — optional toggle in
   *Keybind → Advanced* (default on): show the mouse-wheel / mouse-button /
   `Alt`·`Ctrl`·`Shift`·`Meta` key actually used to cast, rather than a
   leftover plain key. Turn it off for the original first-bound-key behaviour.

A bar-addon override-binding priority change is also included and is
discussed (with its trade-off) in upstream issue #20. Additional findings
reported in #20 (Bartender4 stance override mismatch; a global leak; a
`Core.lua` typo) are **not** patched in this fork — they are upstream-only
suggestions in that issue.

## Install

Copy the `SimpleAssistedCombatIcon-fufu` folder into
`World of Warcraft\_retail_\Interface\AddOns\`.

> **Do not** run this alongside the original SimpleAssistedCombatIcon — both
> use the `SCAIDB` saved variable and will conflict. Enable one or the other.

Retail only (Interface 120001 / 120005). Settings carry over from the
original (same saved variable).

## Credits & license

Original addon © **Katur239** —
<https://github.com/katur239/SimpleAssistedCombatIcon>

This repository publishes **no license over the original code** (upstream
ships none) — it is redistributed in good faith with attribution while the
fixes are upstreamed. See [`LICENSE`](LICENSE) for the full attribution and
good-faith redistribution notice, including takedown contact.

*Some analysis and drafting in this fork was assisted by Claude (Anthropic's
Claude Code); all changes were hand-verified against the sources cited above
and validated in-game.*
