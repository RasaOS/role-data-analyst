# role-data-analyst

**Version:** 0.1.0 · `rasa.module.role.data-analyst` · public

The **Data Analyst** role (`data-analyst`) as a RasaOS role module. The ask needs numbers worked out from data: a calculation, a comparison, a table of figures, a trend or a check of someone else's number

| File | What it is |
|---|---|
| `role.json` | The role's fields (id, name, summary, version, consumers, knowledge, takes, kinds, grants, crew). galt publishes them to `/tenant_config/roles/data-analyst`. |
| `prompt.md` | The role's prompt, from RasaOS/module-crew `content/crew/members/data-analyst.md` at `f6fea0d`. |
| `.claude-plugin/plugin.json` | The plugin manifest, which makes the repo loadable into a session with `--plugin-dir`. |
| `rasa.json` | The Element manifest: `kind: module`, with the role's id and version under `rasa`. |
| `bin/check-role` | The release gate. |

Role version **1**, from RasaOS/module-crew `content/crew/members/data-analyst.md` at `f6fea0d`.

**Crew.** A crew **member** (galt card `data-analyst`). `role.json` `crew` holds that tier's card fields; galt reads them when a crew hires or runs this role.

## Loading it

- **As an agent's brain:** `galt agent new <name> --brain RasaOS/role-data-analyst@v0.1.0`. galt reads `role.json` and `prompt.md`. There is no role assignment this way, so no grants.
- **In a crew:** a crew hires it by its card name `data-analyst` once galt reads crew roles from the role list (tenant ADR 2026-10-28-one-role-list); until then galt runs its in-code copy.
- **Public:** any computer can fetch it. No vault token is needed.

## Changing the role

This repo is the role's source. Change it through a PR on this repo (vsi-tenant's `/role` skill does it): bump `role.json` `version` and the Element version together. Until galt reads crew roles from here, galt's in-code copy must get the same change.
